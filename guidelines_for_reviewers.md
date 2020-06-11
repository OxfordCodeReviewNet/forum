Reviewing code can be intimidating, especially if you don't consider yourself as an experienced programmer.
What if you don't find anything to say?

It is a common misconception to think that reviewers must necesseraly be advanced developpers, and that they must find bugs or make tons of comments for the review to be successful.

Instead, your main job as a reviewer is **simply to ask questions**. This should be easy, as this is rather unlikely that you will understand every line of code without clarifications!
You first goal as a reviewer is to force the code author to explain the detail of their code to you. Doing so, they will very probalby identify bugs and area of improvements **themselves**.

Once you're confortable reading somebeody else's code and asking questions, the next step is to look for potential issues yourself.
If you have no idea what to look for, here is a list of the major points to check in a code review.

## What to look for as a reviewer

*Under construction*

The following points are common guidelines, not rules. Cases may arise where it is best not to follow them.

### Naming
Knowingly the hardest part in software developement.

- Always use descriptive names at every levels, whether it is for variables, functions/methods or classes. Name of functions and classes should convey intent.

> when implmenting mathematical expresions, it's often tempting to name the variable after its mathematical symbol (e.g. `alpha`, `m`, `R0`..).
> This is not recommended, as this makes the code less readable, and other people may use different notations. Use explicit names instead
> (e.g. `streamwise_velocity_field`, `current`, `infection_rate`...)

- Avoid "magic numbers"
```C
for (i=0; i<26;i++){
```
should be
```C
int AlphabetCharacter = 26;
for (i=0; i<AlphabetCharacter ;i++){
```
[See this post by Chris Bertrand](https://dev.to/designpuddle/code-review-checklist-14ke).

### Duplicated code
Copy pasting code may speed up development in the short term... but 
- It cripples the code's maitainability and extendability (either by a colleague or yourself three months down the line).
- Each time you modify a part, you have to remember to modify all duplicated parts without forgetting any. Not only it is boring work, but also error prone.
- Duplicated code also decreases readability, as your code is unnecesraly longer, and makes bug hunting much harder.

Typical solutions include
- Defining new functions/methods that can be reused in differnt parts of the code
- Use class inheritance or composition

### Long functions/methods
- Functions should be as short as possible.
  Readibility an modularity.
- Functions should do one thing.
  Facilitates testing.

### Non-defensive code
Writing defensive code is the art of preventing non-indented behavior.
A typical example is a function with parameters that are constrained (e.g. strictly positive, integer value...).

Example of defensive function:
```python
def compute_acceleration(mass, total_force_on_body):
	if mass <= 0:
		raise ValueError("Mass of body must be strictly positive")
	return total_force_on_body/mass

```

### Documented functions, classes and modules

Any structure should be accompanied by a documentation string (commonly known as *docstring*).
Example
```python
def compute_acceleration(mass, total_force_on_body):
    """
	Compute and return acceleration on body, according to Newton's 2nd law
	
	Parameters
	----------
	mass: float
	  Mass of body
	total_force_on_body: float
	  Sum of all forces exerted on the body
	  
	Returns:
	--------
	a: float
      The acceleration
	"""
	if mass <= 0:
		raise ValueError("Mass of body must be strictly positive")
	return total_force_on_body/mass

```

### Comments
Commenting can be a confusing topic, since the general advice is
> Comment you code, but not too much

The above guudeline can be understood by taking a rather extreme stance: your code should not need comment
to be understood.

Most of the time, comments can be avoided by using more descriptive names, shorter methods, and simpler
constructs.

Comments shpuld describe the *why*, not the *what*.

### Performace low hanging fruits
Typical examples include
- Nested loop ordering
```fortran
implicit none

   integer:: i, j, k
   
   iloop: do i = 1, mesh_size_x
	   jloop: do j = 1, mesh_size_y
         kloop: do k = 1, mesh_size_z
         
	        ! Make sure inner index is last
            a(i, j, k) = prefactor(i, j, k)*(term1(i, j, k) + term2(i, j, k))
            
         end do kloop       
      end do jloop
   end do iloop
```

- Use of local variables
```C++
for (int i; i<stop;i++)
{
  local_var = vector[i];
  result = 2.*local_var*local_var + local_var + 4.
  ...
  
```

### Use built in functions whenever possible
Do not not reinvent the wheel!

Programming languages usually come with useful libraries that implement common tasks.
```python
from itertools import accumulate

accumulate([1,2,3,4,5], initial=100) --> 100 101 103 106 110 115
```

### Leveraging third party libraries




