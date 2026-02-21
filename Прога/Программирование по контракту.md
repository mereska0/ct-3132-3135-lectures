на будущее
```
public class Contract {  
  
    // n >= 0  
    static int power(int a, int n) {  
        // n >= 0  
        int r = 1;  
        // n >= 0 && r == 1 && a == a' && n = n'  
  
        // r * a ^ n == a' ^ n' && n >= 0
        while (n != 0) {  
            // r * a ^ n == a' ^ n' && n > 0  
            if (n % 2 == 1) {  
                // r * a ^ n == a' ^ n' && n > 0 && n % 2 == 1  
                // r * a ^ n == a' ^ n' && n >= 1 && n % 2 == 1                // r * a ^ n == a' ^ n' && (n - 1) >= 0 && n % 2 == 1                // (r * a) * a ^ (n - 1) == a' ^ n' && (n - 1) >= 0 && n % 2 == 1                r = r * a;  
                n = n - 1;  
                // r * a ^ n == a' ^ n' && n >= 0 && n % 2 == 0  
            }  
            // r * a ^ n == a' ^ n' && n >= 0 && n % 2 == 0  
            // r * (a * a) ^ (n / 2) == a' ^ n' && n / 2 >= 0            n = n / 2;  
            a = a * a;  
            // r * a ^ n == a' ^ n' && n >= 0  
        }  
        // r * a ^ n == a' ^ n' && n == 0  
  
        // r = a' ^ n'       
         return r;  
    }  
```
тут пипец какой то полный