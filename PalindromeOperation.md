public class PalindromeOperation {

    public static void main(String[] args) {
        String[] numbers = {"888", "501", "151", "140", "111"};

        for (String num : numbers) {
            boolean isPalindrome = checkPalindrome(num);
            if (isPalindrome) {
                boolean isOperationPalindrome = performOperation(num);
                System.out.println(isOperationPalindrome ? "TRUE" : "FALSE");
            } else {
                System.out.println("FALSE");
            }
        }
    }

    // Method to check if a string is a palindrome
    public static boolean checkPalindrome(String str) {
        int length = str.length();
        for (int i = 0; i < length / 2; i++) {
            if (str.charAt(i) != str.charAt(length - i - 1)) {
                return false;
            }
        }
        return true;
    }

    // Method to perform the specified operation and check if the result is a palindrome
    public static boolean performOperation(String num) {
        int n = Integer.parseInt(num);
        for (int i = 0; i < 3; i++) {
            int reverse = reverseNumber(n);
            n += reverse;
            num = String.valueOf(n);
        }
        return checkPalindrome(num);
    }

    // Method to reverse a number
    public static int reverseNumber(int num) {
        int reversed = 0;
        while (num != 0) {
            reversed = reversed * 10 + num % 10;
            num /= 10;
        }
        return reversed;
    }
}
