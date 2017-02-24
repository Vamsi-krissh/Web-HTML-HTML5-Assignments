# LESS Guidelines #

## Structure. Structure. Structure ##
Make sure structure is organized and created in such a way that accommodates a large project by properly categorizing and modularizing folders and files. It’s better to feel that you’re over-engineering at the beginning, and restructure “down” later, than to assume a minimal set-up up front, simply for the sake of expediency.
	
**Bad:** 

	> less
		*all-of-the-files.less
		
**Good:** 

	> less 
		> modules 
			> global 
				header.less
			> common
				modal.less

## Proper Selector Nesting ##
1. Start with the selector
2. All properties for the selector will go directly underneath the selector
3. Media queries immediately follow properties next to keep property modifiers easily identifiable, and to see which properties are affected by that media query

	**Note:** Nothing except properties for the affected selector should go within media queries.

	**Bad:**

		.my-selector {
			property: value;
	
			@media screen and (min-width: 1024px) {
				property: value;
	
				.another-selector {
					property: value;
				}
	
				property2: value;
			}
	
			property2: value;
		}

	**Good:**
	
		.my-selector {
			property: value;
			property2: value;

			@media screen and (min-width: 1024px) {
				property: value;
				property2: value;
			}

			.another-selector {
				@media screen and (min-width: 1024px) {
					property: value;
				}
			}
		}

4. “&” modifiers go next starting with pseudo selectors (`&:hover`, `&:after`), and then additional class selectors (`&.another-class`)
5. Descendant selectors now follow
6. Avoid placing child selectors within a parent’s just because of a state change. Use proceeding “&” to keep modifications within the child’s scope.

	**Bad:**
		
		.my-selector {
			property: value;

			&.active {
				.another-selector {
					color: red;
				}
			}
		}

		.another-selector {
			color: green;
		}

	**Good:**
	
		.my-selector {
			property: value;
		}

		.another-selector {
			color: green;

			.my-selector.active & {
				color: red;
			}
		}


## Other CSS Requirements ##
1. As long as your classnames are descriptive enough, don’t unnecessarily nest them. Just put them right below.

	**Bad:**
		
		.secondary-nav {
			.secondary-nav-item { … } // Unnecessarily nested
		}
	
	**Good:**
	
		.secondary-nav { … }
		.secondary-nav-item { … }

2. Use only lowercase classnames. Dashes for word separation instead of camelCase

3. For the sake of keeping CSS specificity down and preventing “collisions”, don’t be a lazy typer with class names by using generic names (i.e. “list-item”). Instead, be descriptive (i.e. “secondary-nav-item”). With the former, nesting is required, but with the latter, it is not.

4. Don’t be afraid of adding descriptive classes to every element within a module. If you’re defining a ton of styles for a particular element, it should probably have its own classname, allowing for zero nesting.

5. Avoid element selectors (even nested ones) as much as possible, especially on container elements like `<div>` and `<span>`... except in cases where the element type is least likely to ever change (`<a>` and `<input>` tags).
