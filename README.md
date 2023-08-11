# Java1
Sum of Powers of Three
Given an integer n, return true if it is possible to represent n as the sum of distinct powers of three. Otherwise, return false.
Input Format:
First line of input contains an integer T, which represents the number of test cases.
Next T lines of input contains an integer n.
Constraints:
1 <= T <= 1000
1 <= n <= 10^4
Output Format:
 Print true if it is possibe to represent n as explained, otherwise print false.
Sample Input 1:
1
91
Sample Output 1:
true
Explanation:
3^0 + 3^2 + 3^4
Sample Input 2:
2
12
21
Sample Output 2:
true
false



import java.util.*;

class Solution {
    static public boolean checkPowersOfThree(int n) {
        // Keep subtracting powers of 3 from n
        // until it becomes 0 or negative
        while (n > 0) {
            // Check if the current number is divisible by 3
            if (n % 3 == 2) {
                return false;
            }
            n /= 3;
        }
        return true;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int t = scanner.nextInt(); // Number of test cases

        while (t-- > 0) {
            int n = scanner.nextInt(); // Input integer
            boolean result = checkPowersOfThree(n);
            System.out.println(result ? "true" : "false");
        }
    }
}
