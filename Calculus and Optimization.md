# Calculus and Optimization

### Functions of a Single Variable
- **Definition:** A function $\ f:{R} \to {R} $ where each input $\ x $ from the set of real numbers $\ {R} $ is associated with a unique output $\ f(x) $.
- **Example:** $\ f(x) = x^2 + 3x + 2 $

### Limit
- **Definition:** The value that a function $\ f(x) $ approaches as $\ x $ approaches a certain value $\ c $.
- **Notation:** $\ \lim_{x \to c} f(x) = L $
- **Example:** $\ \lim_{x \to 2} (3x + 1) = 7 $

### Continuity
- **Definition:** A function $\ f(x) $ is continuous at a point $\ c $ if $\ \lim_{x \to c} f(x) = f(c) $.
- **Criteria:** A function is continuous if it is continuous at every point in its domain.

### Differentiability
- **Definition:** A function $\ f(x) $ is differentiable at a point $\ c $ if the derivative $\ f'(c) $ exists.
- **Derivative:** $\ f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h} $
- **Example:** If $\ f(x) = x^2 $, then $\ f'(x) = 2x $.

### Taylor Series
- **Definition:** An infinite sum of terms that are expressed in terms of the function's derivatives at a single point.
- **Formula:** $\ f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!} (x-a)^n $
- **Example:** For $\ f(x) = e^x $, the Taylor series at $\ a=0 $ is $\ e^x = \sum_{n=0}^{\infty} \frac{x^n}{n!} $.

### Maxima and Minima
- **Local Maximum:** A point $\ c $ where $\ f(c) $ is greater than or equal to $\ f(x) $ for all $\ x $ near $\ c $.
- **Local Minimum:** A point $\ c $ where $\ f(c) $ is less than or equal to $\ f(x) $ for all $\ x $ near $\ c $.
- **Critical Points:** Points where $\ f'(x) = 0 $ or $\ f'(x) $ does not exist.
- **Second Derivative Test:** If $\ f''(c) > 0 $, $\ f $ has a local minimum at $\ c $. If $\ f''(c) < 0 $, $\ f $ has a local maximum at $\ c $.

### Optimization Involving a Single Variable
- **Definition:** The process of finding the maximum or minimum value of a function $\ f(x) $.
- **Steps:**
  1. Find the derivative $\ f'(x) $.
  2. Set $\ f'(x) = 0 $ to find critical points.
  3. Use the second derivative test or evaluate $\ f(x) $ at critical points and endpoints to determine maxima or minima.
- **Example:** To maximize $\ f(x) = -x^2 + 4x $, find $\ f'(x) = -2x + 4 $. Set $\ f'(x) = 0 $ to get $\ x = 2 $. Verify $\ f''(2) = -2 $ (negative, so maximum).
