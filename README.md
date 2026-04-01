import java.util.Scanner;
public class int_to_bin_B {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter an integer number: ");
        int number = sc.nextInt();
        
        int[] binaryArray = convertToBinary(number);
        
        System.out.print("Binary representation: ");
        for (int bit : binaryArray) {
            System.out.print(bit);
        }
        sc.close();
    }
    
    public static int[] convertToBinary(int number) {
        StringBuilder binaryString = new StringBuilder();
        
        while (number > 0) {
            int remainder = number % 2;
            binaryString.insert(0, remainder);
            number /= 2;
        }
        
        int[] binaryArray = new int[binaryString.length()];
        for (int i = 0; i < binaryString.length(); i++) {
            binaryArray[i] = Character.getNumericValue(binaryString.charAt(i));
        }
        
        return binaryArray;
    }
}
