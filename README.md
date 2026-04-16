HEAD
# Infix to Prefix and Postfix Converter

## 📌 Description
This Java program converts an infix expression into postfix and prefix forms using a stack data structure.



## 🔄 Workflow

### Infix to Postfix
1. Scan the expression from left to right
2. If operand → add to output
3. If operator → check precedence
4. Use stack to store operators
5. Pop remaining operators at the end

### Infix to Prefix
1. Reverse the infix expression
2. Swap '(' and ')'
3. Convert to postfix
4. Reverse the result to get prefix



## 🧠 Pseudocode

### Infix to PostfixFOR each character ch in expression
    IF ch is operand THEN
        Add ch to P
    ELSE IF ch is '(' THEN
        Push to S
    ELSE IF ch is ')' THEN
        WHILE top of S is not '('
            Pop from S to P
        Pop '('
    ELSE
        WHILE precedence(top of S) >= precedence(ch)
            Pop from S to P
        Push ch to S
END FOR

WHILE S not empty
Pop to P

RETURN P
### Infix to PrefixBEGIN
    Reverse infix expression
    Replace '(' with ')' and vice versa
    Convert to postfix
    Reverse postfix result
    RETURN prefix
END
BEGIN
    Initialize empty stack S
    Initialize empty output P

    FOR each character ch in expression
        IF ch is operand THEN
            Add ch to P
        ELSE IF ch is '(' THEN
            Push to S
        ELSE IF ch is ')' THEN
            WHILE top of S is not '('
                Pop from S to P
            Pop '('
        ELSE
            WHILE precedence(top of S) >= precedence(ch)
                Pop from S to P
            Push ch to S
    END FOR

    WHILE S not empty
        Pop to P

    RETURN P
END
 
