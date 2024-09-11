import java.util.Stack;

public class BrowserHistoryStack {

    public static void main(String[] args) {
        Stack<String> browserHistory = new Stack<>();
        int maxSize = 6;

        System.out.println("Initial Stack: " + browserHistory);

        // 1. Simulate if the stack is full
        System.out.println("\nOperation 1: Check if stack is full");
        checkIfFull(browserHistory, maxSize);

        // 2. Push 2 elements into the stack
        System.out.println("\nOperation 2: Push 2 elements into the stack");
        pushElement(browserHistory, maxSize, "https://site1.com");
        pushElement(browserHistory, maxSize, "https://site2.com");
        System.out.println("Stack after pushing 2 elements: " + browserHistory);

        // 3. Simulate if the stack is full
        System.out.println("\nOperation 3: Check if stack is full");
        checkIfFull(browserHistory, maxSize);

        // 4. Search for all existing elements
        System.out.println("\nOperation 4: Search for all existing elements");
        searchElement(browserHistory, "https://site1.com");
        searchElement(browserHistory, "https://site2.com");

        // 5. Push another 4 elements into the stack
        System.out.println("\nOperation 5: Push another 4 elements into the stack");
        pushElement(browserHistory, maxSize, "https://site3.com");
        pushElement(browserHistory, maxSize, "https://site4.com");
        pushElement(browserHistory, maxSize, "https://site5.com");
        pushElement(browserHistory, maxSize, "https://site6.com");
        System.out.println("Stack after pushing 4 more elements: " + browserHistory);

        // 6. Peek the top element
        System.out.println("\nOperation 6: Peek the top element");
        peekTopElement(browserHistory);

        // 7. Pop six elements from the stack
        System.out.println("\nOperation 7: Pop six elements from the stack");
        popElement(browserHistory);
        popElement(browserHistory);
        popElement(browserHistory);
        popElement(browserHistory);
        popElement(browserHistory);
        popElement(browserHistory);
        System.out.println("Stack after popping all elements: " + browserHistory);

        // 8. Check if the stack is empty
        System.out.println("\nOperation 8: Check if stack is empty");
        checkIfEmpty(browserHistory);
    }

    // Check if the stack is full
    public static void checkIfFull(Stack<String> stack, int maxSize) {
        if (stack.size() == maxSize) {
            System.out.println("The stack is full.");
        } else {
            System.out.println("The stack is not full.");
        }
    }

    // Push an element into the stack
    public static void pushElement(Stack<String> stack, int maxSize, String url) {
        if (stack.size() < maxSize) {
            stack.push(url);
            System.out.println("Pushed: " + url);
        } else {
            System.out.println("Cannot push " + url + ": Stack is full.");
        }
    }

    // Search for an element in the stack
    public static void searchElement(Stack<String> stack, String url) {
        int position = stack.search(url);
        if (position != -1) {
            System.out.println("Found " + url + " at position " + position + " from the top.");
        } else {
            System.out.println(url + " not found in the stack.");
        }
    }

    // Peek the top element of the stack
    public static void peekTopElement(Stack<String> stack) {
        if (!stack.isEmpty()) {
            String topElement = stack.peek();
            System.out.println("Top element is: " + topElement);
        } else {
            System.out.println("Stack is empty. No top element to peek.");
        }
    }

    // Pop an element from the stack
    public static void popElement(Stack<String> stack) {
        if (!stack.isEmpty()) {
            String poppedElement = stack.pop();
            System.out.println("Popped: " + poppedElement);
        } else {
            System.out.println("Cannot pop: Stack is empty.");
        }
    }

    // Check if the stack is empty
    public static void checkIfEmpty(Stack<String> stack) {
        if (stack.isEmpty()) {
            System.out.println("The stack is empty.");
        } else {
            System.out.println("The stack is not empty.");
        }
    }
}
