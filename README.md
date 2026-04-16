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
