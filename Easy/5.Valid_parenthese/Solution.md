# Valid Parentheses
Given a string s containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

Open brackets must be closed by the same type of brackets.
Open brackets must be closed in the correct order.
Every close bracket has a corresponding open bracket of the same type.
 

Example 1:

Input: s = "()"

Output: true

Example 2:

Input: s = "()[]{}"

Output: true

Example 3:

Input: s = "(]"

Output: false

Example 4:

Input: s = "([])"

Output: true

## Solution
1. User the stack to save open brackets like {[(.
2. Then check if there is a suitable closed brackets if any, remove from the stack.

### Code
	public boolean isValid(String s) {
		Stack<Character> stack = new Stack<Character>();
		
		for(int i = 0 ; i < s.length() ; i++) {
			if(s.charAt(i) == '{' || s.charAt(i) == '[' || s.charAt(i) == '(') {
				stack.push(s.charAt(i));
			}else {
				if(!stack.isEmpty() && (stack.getLast() == '('&& s.charAt(i) == ')' ||
						stack.getLast() == '{' && s.charAt(i) == '}') || 
						stack.getLast() == '[' && s.charAt(i) == ']') {
					
					stack.pop();
				}else {
					return false;
				}
			}
		}
		return stack.isEmpty();
	}