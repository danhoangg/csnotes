
### Injective Functions
A function $f: X\to Y$ is injective if it satisfies:
- For all x,x' in X, $f(x)=f(x')$ implies that x=x'
- Basically, different elements map to different elements

### Surjective Functions
A function $f:X\to Y$ is surjective if for all $y\in Y$ there exists an $x\in X$ such that $f(x)=y$
Basically, if all of Y is the range, then $f$ is surjective


### Bijective Functions
A function that is both **surjective** and **injective** is a bijective function, and also implies that the function has an inverse

### Isomorphism theorem

Prove that "bijective" = "has inverse":
- Prove that *bijective* implies *has inverse*
- If a function is bijective then for every element $y\in Y$ there is a unique element $x\in X$ such that $f(x)=y$.  Which allows $f^{-1}(y)=x$ define a function $f^{-1}:Y\to X$ 

- Prove that *has inverse* implies *bijective*
- Suppose that for some $x,x'\in X$ and that $f(x)=f(x')$, apply inverse function to both sides: $f^{-1}(f(x))=f^{-1}(f(x'))$ which means that $x=x'$ so $f$ is injective
- Suppose that $y\in Y$. We need to find $x\in X$ such that $f(x)=y$. Take $x=f^{-1}(y)$ then $f(x)=f(f^{-1}(y))=y$ which means that $f$ is surjective.
- Therefore inverse implies bijective