---
layout: single
title: 'EditorConfig Coding conventions'
permalink: /editorconfig/coding-conventions
toc: true
toc_sticky: true
---

## .NET Coding Conventions
[*.{cs,vb}] for all C# and VB files.


### Expression-level preferences
````csharp
dotnet_style_collection_initializer                         = true : suggestion
dotnet_style_explicit_tuple_names                           = true : suggestion
dotnet_style_object_initializer                             = true : suggestion
dotnet_style_prefer_auto_properties                         = true : silent
dotnet_style_prefer_compound_assignment                     = true : suggestion
dotnet_style_prefer_conditional_expression_over_assignment  = true : silent
dotnet_style_prefer_conditional_expression_over_return      = true : silent
dotnet_style_prefer_inferred_anonymous_type_member_names    = true : suggestion
dotnet_style_prefer_inferred_tuple_names                    = true : suggestion
dotnet_style_prefer_simplified_boolean_expressions          = true : suggestion
dotnet_style_prefer_simplified_interpolation                = true : suggestion
# Add missing cases to switch statement - This rule has no code style option.
# Convert anonymous type to tuple - This rule has no code style option.
# Use 'System.HashCode.Combine' - This rule has no code style option.
# Convert 'typeof' to 'nameof' - This rule has no code style option.
````

- [dotnet_style_collection_initializer](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0028#dotnet_style_collection_initializer)
    ````csharp
    // dotnet_style_collection_initializer = true
    var list = new List<int> { 1, 2, 3 };

    // dotnet_style_collection_initializer = false
    var list = new List<int>();
    list.Add(1);
    list.Add(2);
    list.Add(3);
    ````
- [dotnet_style_explicit_tuple_names](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0033#dotnet_style_explicit_tuple_names)
    ````csharp
    // dotnet_style_explicit_tuple_names = true
    (string name, int age) customer = GetCustomer();
    var name = customer.name;

    // dotnet_style_explicit_tuple_names = false
    (string name, int age) customer = GetCustomer();
    var name = customer.Item1;
    ````
- [dotnet_style_object_initializer](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0017#dotnet_style_object_initializer)
    ````csharp
    // dotnet_style_object_initializer = true
    var c = new Customer() { Age = 21 };

    // dotnet_style_object_initializer = false
    var c = new Customer();
    c.Age = 21;
    ````
- [dotnet_style_prefer_auto_properties](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0032#dotnet_style_prefer_auto_properties)
    ````csharp
    // dotnet_style_prefer_auto_properties = true
    private int Age { get; }

    // dotnet_style_prefer_auto_properties = false
    private int age;

    public int Age
    {
        get
        {
            return age;
        }
    }
    ````
- [dotnet_style_prefer_compound_assignment](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0054-ide0074#dotnet_style_prefer_compound_assignment)
    ````csharp
    // dotnet_style_prefer_compound_assignment = true
    x += 1;

    // dotnet_style_prefer_compound_assignment = false
    x = x + 1;
    ````
- [dotnet_style_prefer_conditional_expression_over_assignment](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0045#dotnet_style_prefer_conditional_expression_over_assignment)
    ````csharp
    // dotnet_style_prefer_conditional_expression_over_assignment = true
    string s = expr ? "hello" : "world";

    // dotnet_style_prefer_conditional_expression_over_assignment = false
    string s;
    if (expr)
    {
        s = "hello";
    }
    else
    {
        s = "world";
    }
    ````
- [dotnet_style_prefer_conditional_expression_over_return](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0046#dotnet_style_prefer_conditional_expression_over_return)
    ````csharp
    // dotnet_style_prefer_conditional_expression_over_return = true
    return expr ? "hello" : "world"

    // dotnet_style_prefer_conditional_expression_over_return = false
    if (expr)
    {
        return "hello";
    }
    else
    {
        return "world";
    }
    ````
- [dotnet_style_prefer_inferred_anonymous_type_member_names](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0037#dotnet_style_prefer_inferred_anonymous_type_member_names)
    ````csharp
    // dotnet_style_prefer_inferred_anonymous_type_member_names = true
    var anon = new { age, name };

    // dotnet_style_prefer_inferred_anonymous_type_member_names = false
    var anon = new { age = age, name = name };
    ````
- [dotnet_style_prefer_inferred_tuple_names](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0037#dotnet_style_prefer_inferred_tuple_names)
    ````csharp
    // dotnet_style_prefer_inferred_tuple_names = true
    var tuple = (age, name);

    // dotnet_style_prefer_inferred_tuple_names = false
    var tuple = (age: age, name: name);
    ````
- [dotnet_style_prefer_simplified_boolean_expressions](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0075#dotnet_style_prefer_simplified_boolean_expressions)
    ````csharp
    // dotnet_style_prefer_simplified_boolean_expressions = true
    var result1 = M1() && M2();
    var result2 = M1() || M2();

    // dotnet_style_prefer_simplified_boolean_expressions = false
    var result1 = M1() && M2() ? true : false;
    var result2 = M1() ? true : M2();
    ````
- [dotnet_style_prefer_simplified_interpolation](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0071#dotnet_style_prefer_simplified_interpolation)
    ````csharp
    // dotnet_style_prefer_simplified_interpolation = true
    var str = $"prefix {someValue} suffix";

    // dotnet_style_prefer_simplified_interpolation = false
    var str = $"prefix {someValue.ToString()} suffix";
    ````

### Expression-bodied members
````csharp
csharp_style_expression_bodied_accessors        = true : silent
csharp_style_expression_bodied_constructors     = false : silent
csharp_style_expression_bodied_indexers         = true : silent
csharp_style_expression_bodied_lambdas          = true : silent
csharp_style_expression_bodied_local_functions  = false : silent
csharp_style_expression_bodied_methods          = false : silent
csharp_style_expression_bodied_operators        = false : silent
csharp_style_expression_bodied_properties       = true : silent
````
- [csharp_style_expression_bodied_accessors](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0027#csharp_style_expression_bodied_accessors)
    ````csharp
    // csharp_style_expression_bodied_accessors = true
    public int Age { get => _age; set => _age = value; }

    // csharp_style_expression_bodied_accessors = false
    public int Age { get { return _age; } set { _age = value; } }
    ````
- [csharp_style_expression_bodied_constructors](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0021#csharp_style_expression_bodied_constructors)
    ````csharp
    // csharp_style_expression_bodied_constructors = true
    public Customer(int age) => Age = age;

    // csharp_style_expression_bodied_constructors = false
    public Customer(int age) { Age = age; }
    ````
- [csharp_style_expression_bodied_indexers](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0026#csharp_style_expression_bodied_indexers)
    ````csharp
    // csharp_style_expression_bodied_indexers = true
    public T this[int i] => _values[i];

    // csharp_style_expression_bodied_indexers = false
    public T this[int i] { get { return _values[i]; } }
    ````
- [csharp_style_expression_bodied_lambdas](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0053#csharp_style_expression_bodied_lambdas)
    ````csharp
    // csharp_style_expression_bodied_lambdas = true
    Func<int, int> square = x => x * x;

    // csharp_style_expression_bodied_lambdas = false
    Func<int, int> square = x => { return x * x; };
    ````
- [csharp_style_expression_bodied_local_functions](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0061#csharp_style_expression_bodied_local_functions)
    ````csharp
    // csharp_style_expression_bodied_local_functions = true
    void M()
    {
        Hello();
        void Hello() => Console.WriteLine("Hello");
    }

    // csharp_style_expression_bodied_local_functions = false
    void M()
    {
        Hello();
        void Hello()
        {
            Console.WriteLine("Hello");
        }
    }
    ````
- [csharp_style_expression_bodied_methods](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0022#csharp_style_expression_bodied_methods)
    ````csharp
    // csharp_style_expression_bodied_methods = true
    public int GetAge() => this.Age;

    // csharp_style_expression_bodied_methods = false
    public int GetAge() { return this.Age; }
    ````
- [csharp_style_expression_bodied_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0023-ide0024#csharp_style_expression_bodied_operators)
    ````csharp
    // csharp_style_expression_bodied_operators = true
    public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
        => new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary);

    // csharp_style_expression_bodied_operators = false
    public static ComplexNumber operator + (ComplexNumber c1, ComplexNumber c2)
    { return new ComplexNumber(c1.Real + c2.Real, c1.Imaginary + c2.Imaginary); }
    ````
- [csharp_style_expression_bodied_properties](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0025#csharp_style_expression_bodied_properties)
    ````csharp
    // csharp_style_expression_bodied_properties = true
    public int Age => _age;

    // csharp_style_expression_bodied_properties = false
    public int Age { get { return _age; }}
    ````

### Indentation and spacing
````csharp
csharp_indent_block_contents            = true
csharp_indent_braces                    = false
csharp_indent_case_contents             = true
csharp_indent_case_contents_when_block  = true
csharp_indent_labels                    = one_less_than_current
csharp_indent_switch_labels             = false
````

- [csharp_indent_case_contents](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_case_contents)
    ````csharp
    // csharp_indent_case_contents = true
    switch(c) {
        case Color.Red:
            Console.WriteLine("The color is red");
            break;
        case Color.Blue:
            Console.WriteLine("The color is blue");
            break;
        default:
            Console.WriteLine("The color is unknown.");
            break;
    }

    // csharp_indent_case_contents = false
    switch(c) {
        case Color.Red:
        Console.WriteLine("The color is red");
        break;
        case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
        default:
        Console.WriteLine("The color is unknown.");
        break;
    }
    ````
- [csharp_indent_switch_labels](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_switch_labels)
    ````csharp
    // csharp_indent_switch_labels = true
    switch(c) {
        case Color.Red:
            Console.WriteLine("The color is red");
            break;
        case Color.Blue:
            Console.WriteLine("The color is blue");
            break;
        default:
            Console.WriteLine("The color is unknown.");
            break;
    }

    // csharp_indent_switch_labels = false
    switch(c) {
    case Color.Red:
        Console.WriteLine("The color is red");
        break;
    case Color.Blue:
        Console.WriteLine("The color is blue");
        break;
    default:
        Console.WriteLine("The color is unknown.");
        break;
    }
    ````
- [csharp_indent_labels](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_labels)
    ````csharp
    // csharp_indent_labels= flush_left
    class C
    {
        private string MyMethod(...)
        {
            if (...) {
                goto error;
            }
    error:
            throw new Exception(...);
        }
    }

    // csharp_indent_labels = one_less_than_current
    class C
    {
        private string MyMethod(...)
        {
            if (...) {
                goto error;
            }
        error:
            throw new Exception(...);
        }
    }

    // csharp_indent_labels= no_change
    class C
    {
        private string MyMethod(...)
        {
            if (...) {
                goto error;
            }
            error:
            throw new Exception(...);
        }
    }
    ````
- [csharp_indent_block_contents](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_block_contents)
    ````csharp
    // csharp_indent_block_contents = true
    static void Hello()
    {
        Console.WriteLine("Hello");
    }

    // csharp_indent_block_contents = false
    static void Hello()
    {
    Console.WriteLine("Hello");
    }
    ````
- [csharp_indent_braces](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_braces)
    ````csharp
    // csharp_indent_braces = true
    static void Hello()
        {
        Console.WriteLine("Hello");
        }

    // csharp_indent_braces = false
    static void Hello()
    {
        Console.WriteLine("Hello");
    }
    ````
- [csharp_indent_case_contents_when_block](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_indent_case_contents_when_block)
    ````csharp
    // csharp_indent_case_contents_when_block = true
    case 0:
        {
            Console.WriteLine("Hello");
            break;
        }

    // csharp_indent_case_contents_when_block = false
    case 0:
    {
        Console.WriteLine("Hello");
        break;
    }
    ````

### Language keywords vs BCL types preferences
````csharp
dotnet_style_predefined_type_for_locals_parameters_members  = true : error
dotnet_style_predefined_type_for_member_access              = true : error
````

- [dotnet_style_predefined_type_for_locals_parameters_members](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0049#dotnet_style_predefined_type_for_locals_parameters_members)
    ````csharp
    // dotnet_style_predefined_type_for_locals_parameters_members = true
    private int _member;
    
    // dotnet_style_predefined_type_for_locals_parameters_members = false
    private Int32 _member;
    ````
- [dotnet_style_predefined_type_for_member_access](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0049#dotnet_style_predefined_type_for_member_access)
    ````csharp
    // dotnet_style_predefined_type_for_member_access = true
    var local = int.MaxValue;
    
    // dotnet_style_predefined_type_for_member_access = false
    var local = Int32.MaxValue;
    ````

### Modifier preferences
````csharp
csharp_prefer_static_local_function             = true : suggestion
csharp_preferred_modifier_order                 = public, private, protected, internal, static, extern, new, virtual, abstract, sealed, override, readonly, unsafe, volatile, async:silent
dotnet_style_readonly_field                     = true : suggestion
dotnet_style_require_accessibility_modifiers    = for_non_interface_members : silent
visual_basic_preferred_modifier_order           = Partial, Default, Private, Protected, Public, Friend, NotOverridable, Overridable, MustOverride, Overloads, Overrides, MustInherit, NotInheritable, Static, Shared, Shadows, ReadOnly, WriteOnly, Dim, Const, WithEvents, Widening, Narrowing, Custom, Async:silent
````

- [csharp_prefer_static_local_function](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0062#csharp_prefer_static_local_function)	
    ````csharp
    // csharp_prefer_static_local_function = true
    void M()
    {
        Hello();
        static void Hello()
        {
            Console.WriteLine("Hello");
        }
    }
    
    // csharp_prefer_static_local_function = false
    void M()
    {
        Hello();
        void Hello()
        {
            Console.WriteLine("Hello");
        }
    }
    ````
- [csharp_preferred_modifier_order](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0036#csharp_preferred_modifier_order)	
    ````csharp
    // csharp_preferred_modifier_order = public,private,protected,internal,static,extern,new,virtual,abstract,sealed,override,readonly,unsafe,volatile,async
    class MyClass
    {
        private static readonly int _daysInYear = 365;
    }
    ````	
- [dotnet_style_readonly_field](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0044#dotnet_style_readonly_field)		
    ````csharp
    // dotnet_style_readonly_field = true
    class MyClass
    {
        private readonly int _daysInYear = 365;
    }
    ````	
- [dotnet_style_require_accessibility_modifiers](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0040#dotnet_style_require_accessibility_modifiers)
    ````csharp
    // dotnet_style_require_accessibility_modifiers = always
    // dotnet_style_require_accessibility_modifiers = for_non_interface_members
    class MyClass
    {
        private const string thisFieldIsConst = "constant";
    }
    
    // dotnet_style_require_accessibility_modifiers = never
    class MyClass
    {
        const string thisFieldIsConst = "constant";
    }
    ````
- [visual_basic_preferred_modifier_order](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0036#visual_basic_preferred_modifier_order)
    ````csharp
    ' visual_basic_preferred_modifier_order = Partial,Default,Private,Protected,Public,Friend,NotOverridable,Overridable,MustOverride,Overloads,Overrides,MustInherit,NotInheritable,Static,Shared,Shadows,ReadOnly,WriteOnly,Dim,Const,WithEvents,Widening,Narrowing,Custom,Async
    Public Class MyClass
        Private Shared ReadOnly daysInYear As Int = 365
    End Class
    ````

### New line preferences
````csharp
csharp_new_line_before_catch                            = true
csharp_new_line_before_else                             = true
csharp_new_line_before_finally                          = true
csharp_new_line_before_members_in_anonymous_types       = true
csharp_new_line_before_members_in_object_initializers   = true
csharp_new_line_before_open_brace                       = all
csharp_new_line_between_query_expression_clauses        = true
````

- [csharp_new_line_before_open_brace](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_open_brace)
    ````csharp
    // csharp_new_line_before_open_brace = all
    void MyMethod()
    {
        if (...)
        {
            ...
        }
    }
    
    // csharp_new_line_before_open_brace = none
    void MyMethod() {
        if (...) {
            ...
        }
    }
    ````
- [csharp_new_line_before_else](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_else)
    ````csharp
    // csharp_new_line_before_else = true
    if (...) {
        ...
    }
    else {
        ...
    }
    
    // csharp_new_line_before_else = false
    if (...) {
        ...
    } else {
        ...
    }
    ````
- [csharp_new_line_before_catch](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_catch)
    ````csharp
    // csharp_new_line_before_catch = true
    try {
        ...
    }
    catch (Exception e) {
        ...
    }

    // csharp_new_line_before_catch = false
    try {
        ...
    } catch (Exception e) {
        ...
    }
    ````
- [csharp_new_line_before_finally](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_finally)
    ````csharp
    // csharp_new_line_before_finally = true
    try {
        ...
    }
    catch (Exception e) {
        ...
    }
    finally {
        ...
    }

    // csharp_new_line_before_finally = false
    try {
        ...
    } catch (Exception e) {
        ...
    } finally {
        ...
    }
    ````
- [csharp_new_line_before_members_in_object_initializers](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_members_in_object_initializers)
    ````csharp
    // csharp_new_line_before_members_in_object_initializers = true
    var z = new B()
    {
        A = 3,
        B = 4
    }

    // csharp_new_line_before_members_in_object_initializers = false
    var z = new B()
    {
        A = 3, B = 4
    }
    ````
- [csharp_new_line_before_members_in_anonymous_types](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_before_members_in_anonymous_types)
    ````csharp
    // csharp_new_line_before_members_in_anonymous_types = true
    var z = new
    {
        A = 3,
        B = 4
    }
    
    // csharp_new_line_before_members_in_anonymous_types = false
    var z = new
    {
        A = 3, B = 4
    }
    ````
- [csharp_new_line_between_query_expression_clauses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_new_line_between_query_expression_clauses)
    ````csharp
    // csharp_new_line_between_query_expression_clauses = true
    var q = from a in e
            from b in e
            select a * b;
    
    // csharp_new_line_between_query_expression_clauses = false
    var q = from a in e from b in e
            select a * b;
    ````

### Null-checking preferences
````csharp
csharp_style_conditional_delegate_call                              = true : suggestion
dotnet_style_coalesce_expression                                    = true : suggestion
dotnet_style_null_propagation                                       = true : suggestion
dotnet_style_prefer_is_null_check_over_reference_equality_method    = true : suggestion
````

- [csharp_style_conditional_delegate_call](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide1005)
    ````csharp
    // csharp_style_conditional_delegate_call = true
    func?.Invoke(args);

    // csharp_style_conditional_delegate_call = false
    if (func != null) { func(args); }
    ````
- [dotnet_style_coalesce_expression](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0029-ide0030#dotnet_style_coalesce_expression)
    ````csharp
    // dotnet_style_coalesce_expression = true
    var v = x ?? y;

    // dotnet_style_coalesce_expression = false
    var v = x != null ? x : y; // or
    var v = x == null ? y : x;
    ````
- [dotnet_style_null_propagation](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0031#dotnet_style_null_propagation)
    ````csharp
    // dotnet_style_null_propagation = true
    var v = o?.ToString();

    // dotnet_style_null_propagation = false
    var v = o == null ? null : o.ToString(); // or
    var v = o != null ? o.String() : null;
    ````
- [dotnet_style_prefer_is_null_check_over_reference_equality_method](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0041#dotnet_style_prefer_is_null_check_over_reference_equality_method)
    ````csharp
    // dotnet_style_prefer_is_null_check_over_reference_equality_method = true
    if (value is null)
        return;

    // dotnet_style_prefer_is_null_check_over_reference_equality_method = false
    if (object.ReferenceEquals(value, null))
        return;
    ````


### Parentheses preferences
````csharp
dotnet_style_parentheses_in_arithmetic_binary_operators     = always_for_clarity : silent
dotnet_style_parentheses_in_other_binary_operators          = always_for_clarity : silent
dotnet_style_parentheses_in_other_operators                 = never_if_unnecessary : silent
dotnet_style_parentheses_in_relational_binary_operators     = always_for_clarity : silent
````

- [dotnet_style_parentheses_in_arithmetic_binary_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0047-ide0048#dotnet_style_parentheses_in_arithmetic_binary_operators)
    ````csharp
    // dotnet_style_parentheses_in_arithmetic_binary_operators = always_for_clarity
    var v = a + (b * c);

    // dotnet_style_parentheses_in_arithmetic_binary_operators = never_if_unnecessary
    var v = a + b * c;
    ````
- [dotnet_style_parentheses_in_other_binary_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0047-ide0048#dotnet_style_parentheses_in_other_binary_operators)
    ````csharp
    // dotnet_style_parentheses_in_other_binary_operators = always_for_clarity
    var v = a || (b && c);

    // dotnet_style_parentheses_in_other_binary_operators = never_if_unnecessary
    var v = a || b && c;
    ````
- [dotnet_style_parentheses_in_other_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0047-ide0048#dotnet_style_parentheses_in_other_operators)
    ````csharp
    // dotnet_style_parentheses_in_other_operators = always_for_clarity
    var v = (a.b).Length;

    // dotnet_style_parentheses_in_other_operators = never_if_unnecessary
    var v = a.b.Length;
    ````
- [dotnet_style_parentheses_in_relational_binary_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0047-ide0048#dotnet_style_parentheses_in_relational_binary_operators)
    ````csharp
    // dotnet_style_parentheses_in_relational_binary_operators = always_for_clarity
    var v = (a < b) == (c > d);

    // dotnet_style_parentheses_in_relational_binary_operators = never_if_unnecessary
    var v = a < b == c > d;
    ````

### Pattern matching preferences
````csharp
csharp_style_pattern_matching_over_as_with_null_check   = true : suggestion
csharp_style_pattern_matching_over_is_with_cast_check   = true : suggestion
csharp_style_prefer_not_pattern                         = true : suggestion
csharp_style_prefer_pattern_matching                    = true : silent
csharp_style_prefer_switch_expression                   = true : suggestion
````

- [csharp_style_pattern_matching_over_as_with_null_check](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0019#csharp_style_pattern_matching_over_as_with_null_check)
    ````csharp
    // csharp_style_pattern_matching_over_as_with_null_check = true
    if (o is string s) {...}

    // csharp_style_pattern_matching_over_as_with_null_check = false
    var s = o as string;
    if (s != null) {...}
    ````
- [csharp_style_pattern_matching_over_is_with_cast_check](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0020-ide0038#csharp_style_pattern_matching_over_is_with_cast_check)
    ````csharp
    // csharp_style_pattern_matching_over_is_with_cast_check = true
    if (o is int i) {...}

    // csharp_style_pattern_matching_over_is_with_cast_check = false
    if (o is int) {var i = (int)o; ... }
    ````
- [csharp_style_prefer_not_pattern](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0083#csharp_style_prefer_not_pattern)
    ````csharp
    // csharp_style_prefer_not_pattern = true
    var y = o is not C c;

    // csharp_style_prefer_not_pattern = false
    var y = !(o is C c);
    ````
- [csharp_style_prefer_pattern_matching](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0078#csharp_style_prefer_pattern_matching)
    ````csharp
    // csharp_style_prefer_pattern_matching = true
    var x = i is default(int) or > (default(int));
    var y = o is not C c;

    // csharp_style_prefer_pattern_matching = false
    var x = i == default || i > default(int);
    var y = !(o is C c);
    ````
- [csharp_style_prefer_switch_expression](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0066#csharp_style_prefer_switch_expression)
    ````csharp
    // csharp_style_prefer_switch_expression = true
    return x switch
    {
        1 => 1 * 1,
        2 => 2 * 2,
        _ => 0,
    };

    // csharp_style_prefer_switch_expression = false
    switch (x)
    {
        case 1:
            return 1 * 1;
        case 2:
            return 2 * 2;
        default:
            return 0;
    }
    ````


### this. and Me. preferences
````csharp
dotnet_style_qualification_for_event    = false : error
dotnet_style_qualification_for_field    = false : error
dotnet_style_qualification_for_method   = false : error
dotnet_style_qualification_for_property = false : error
````

- [dotnet_style_qualification_for_event](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0003-ide0009#dotnet_style_qualification_for_event)
    ````csharp
    // dotnet_style_qualification_for_event = true
    this.Elapsed += Handler;
    
    // dotnet_style_qualification_for_event = false
    Elapsed += Handler;
    ````
- [dotnet_style_qualification_for_field](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0003-ide0009#dotnet_style_qualification_for_field)
    ````csharp
    // dotnet_style_qualification_for_field = true
    this.capacity = 0;
    
    // dotnet_style_qualification_for_field = false
    capacity = 0;
    ````
- [dotnet_style_qualification_for_method](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0003-ide0009#dotnet_style_qualification_for_method)
    ````csharp
    // dotnet_style_qualification_for_method = true
    this.Display();
    
    // dotnet_style_qualification_for_method = false
    Display();
    ````
- [dotnet_style_qualification_for_property](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0003-ide0009#dotnet_style_qualification_for_property)
    ````csharp
    // dotnet_style_qualification_for_property = true
    this.ID = 0;
    
    // dotnet_style_qualification_for_property = false
    ID = 0;
    ````

### Organize usings
````csharp
csharp_using_directive_placement        = outside_namespace : error
dotnet_separate_import_directive_groups = false : warning
dotnet_sort_system_directives_first     = true : warning
file_header_template                    = unset
````

- [csharp_using_directive_placement](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#using-directive-options)
    ````csharp
    // csharp_using_directive_placement = outside_namespace
    using System;

    namespace Conventions
    {
        ...
    }

    // csharp_using_directive_placement = inside_namespace
    namespace Conventions
    {
        using System;
        ...
    }
    ````
- [dotnet_separate_import_directive_groups](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#dotnet_separate_import_directive_groups)
    ````csharp
    // dotnet_separate_import_directive_groups = true
    using System.Collections.Generic;
    using System.Threading.Tasks;
    
    using Octokit;
    
    // dotnet_separate_import_directive_groups = false
    using System.Collections.Generic;
    using System.Threading.Tasks;
    using Octokit;
    ````
- [dotnet_sort_system_directives_first](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#dotnet_sort_system_directives_first)
    ````csharp
    // dotnet_sort_system_directives_first = true
    using System.Collections.Generic;
    using System.Threading.Tasks;
    using Octokit;
    
    // dotnet_sort_system_directives_first = false
    using System.Collections.Generic;
    using Octokit;
    using System.Threading.Tasks;
    ````
- [file_header_template](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0073#file_header_template)
    ````csharp
    // file_header_template = Copyright (c) SomeCorp. All rights reserved.\nLicensed under the xyz license.

    // Copyright (c) SomeCorp. All rights reserved.\nLicensed under the xyz license.
    namespace N1
    {
        class C1 { }
    }

    // file_header_template = unset
    //      OR
    // file_header_template =
    namespace N2
    {
        class C2 { }
    }
    ````

### Parameter preferences
````csharp
dotnet_code_quality_unused_parameters									= all : suggestion
````

- [dotnet_code_quality_unused_parameters (IDE0060)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0060#dotnet_code_quality_unused_parameters)
    ````csharp
    // dotnet_code_quality_unused_parameters = all
    public int GetNum1(int unusedParam) { return 1; }
    internal int GetNum2(int unusedParam) { return 1; }
    private int GetNum3(int unusedParam) { return 1; }

    // dotnet_code_quality_unused_parameters = non_public
    internal int GetNum4(int unusedParam) { return 1; }
    private int GetNum5(int unusedParam) { return 1; }
    ````

### Spacing
````csharp
csharp_space_after_cast                                                     = false
csharp_space_after_colon_in_inheritance_clause                              = true
csharp_space_after_comma                                                    = true
csharp_space_after_dot                                                      = false
csharp_space_after_keywords_in_control_flow_statements                      = true
csharp_space_after_semicolon_in_for_statement                               = true
csharp_space_around_binary_operators                                        = before_and_after
csharp_space_around_declaration_statements                                  = false
csharp_space_before_colon_in_inheritance_clause                             = true
csharp_space_before_comma                                                   = false
csharp_space_before_dot                                                     = false
csharp_space_before_open_square_brackets                                    = false
csharp_space_before_semicolon_in_for_statement                              = false
csharp_space_between_empty_square_brackets                                  = false
csharp_space_between_method_call_empty_parameter_list_parentheses           = false
csharp_space_between_method_call_name_and_opening_parenthesis               = false
csharp_space_between_method_call_parameter_list_parentheses                 = false
csharp_space_between_method_declaration_empty_parameter_list_parentheses    = false
csharp_space_between_method_declaration_name_and_open_parenthesis           = false
csharp_space_between_method_declaration_parameter_list_parentheses          = false
csharp_space_between_parentheses                                            = false
csharp_space_between_square_brackets                                        = false
````

- [csharp_space_after_cast](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_cast)
    ````csharp
    // csharp_space_after_cast = true
    int y = (int) x;

    // csharp_space_after_cast = false
    int y = (int)x;
    ````
- [csharp_space_after_keywords_in_control_flow_statements](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_keywords_in_control_flow_statements)
    ````csharp
    // csharp_space_after_keywords_in_control_flow_statements = true
    for (int i;i<x;i++) { ... }

    // csharp_space_after_keywords_in_control_flow_statements = false
    for(int i;i<x;i++) { ... }
    ````
- [csharp_space_between_parentheses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_parentheses)
    ````csharp
    // csharp_space_between_parentheses = control_flow_statements
    for ( int i = 0; i < 10; i++ ) { }

    // csharp_space_between_parentheses = expressions
    var z = ( x * y ) - ( ( y - x ) * 3 );

    // csharp_space_between_parentheses = type_casts
    int y = ( int )x;
    ````
- [csharp_space_before_colon_in_inheritance_clause](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_before_colon_in_inheritance_clause)
    ````csharp
    // csharp_space_before_colon_in_inheritance_clause = true
    interface I
    {

    }

    class C : I
    {

    }

    // csharp_space_before_colon_in_inheritance_clause = false
    interface I
    {

    }

    class C: I
    {

    }
    ````
- [csharp_space_after_colon_in_inheritance_clause](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_colon_in_inheritance_clause)
    ````csharp
    // csharp_space_after_colon_in_inheritance_clause = true
    interface I
    {

    }

    class C : I
    {

    }

    // csharp_space_after_colon_in_inheritance_clause = false
    interface I
    {

    }

    class C :I
    {

    }
    ````
- [csharp_space_around_binary_operators](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_around_binary_operators)
    ````csharp
    // csharp_space_around_binary_operators = before_and_after
    return x * (x - y);

    // csharp_space_around_binary_operators = none
    return x*(x-y);

    // csharp_space_around_binary_operators = ignore
    return x  *  (x-y);
    ````
- [csharp_space_between_method_declaration_parameter_list_parentheses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_declaration_parameter_list_parentheses)
    ````csharp
    // csharp_space_between_method_declaration_parameter_list_parentheses = true
    void Bark( int x ) { ... }

    // csharp_space_between_method_declaration_parameter_list_parentheses = false
    void Bark(int x) { ... }
    ````
- [csharp_space_between_method_declaration_empty_parameter_list_parentheses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_declaration_empty_parameter_list_parentheses)
    ````csharp
    // csharp_space_between_method_declaration_empty_parameter_list_parentheses = true
    void Goo( )
    {
        Goo(1);
    }

    void Goo(int x)
    {
        Goo();
    }

    // csharp_space_between_method_declaration_empty_parameter_list_parentheses = false
    void Goo()
    {
        Goo(1);
    }

    void Goo(int x)
    {
        Goo();
    }
    ````
- [csharp_space_between_method_declaration_name_and_open_parenthesis](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_declaration_name_and_open_parenthesis)
    ````csharp
    // csharp_space_between_method_declaration_name_and_open_parenthesis = true
    void M () { }

    // csharp_space_between_method_declaration_name_and_open_parenthesis = false
    void M() { }
    ````
- [csharp_space_between_method_call_parameter_list_parentheses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_call_parameter_list_parentheses)
    ````csharp
    // csharp_space_between_method_call_parameter_list_parentheses = true
    MyMethod( argument );

    // csharp_space_between_method_call_parameter_list_parentheses = false
    MyMethod(argument);
    ````
- [csharp_space_between_method_call_empty_parameter_list_parentheses](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_call_empty_parameter_list_parentheses)
    ````csharp
    // csharp_space_between_method_call_empty_parameter_list_parentheses = true
    void Goo()
    {
        Goo(1);
    }

    void Goo(int x)
    {
        Goo( );
    }

    // csharp_space_between_method_call_empty_parameter_list_parentheses = false
    void Goo()
    {
        Goo(1);
    }

    void Goo(int x)
    {
        Goo();
    }
    ````
- [csharp_space_between_method_call_name_and_opening_parenthesis](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_method_call_name_and_opening_parenthesis)
    ````csharp
    // csharp_space_between_method_call_name_and_opening_parenthesis = true
    void Goo()
    {
        Goo (1);
    }

    void Goo(int x)
    {
        Goo ();
    }

    // csharp_space_between_method_call_name_and_opening_parenthesis = false
    void Goo()
    {
        Goo(1);
    }

    void Goo(int x)
    {
        Goo();
    }
    ````
- [csharp_space_after_comma](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_comma)
    ````csharp
    // csharp_space_after_comma = true
    int[] x = new int[] { 1, 2, 3, 4, 5 };

    // csharp_space_after_comma = false
    int[] x = new int[] { 1,2,3,4,5 }
    ````
- [csharp_space_before_comma](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_before_comma)
    ````csharp
    // csharp_space_before_comma = true
    int[] x = new int[] { 1 , 2 , 3 , 4 , 5 };

    // csharp_space_before_comma = false
    int[] x = new int[] { 1, 2, 3, 4, 5 };
    ````
- [csharp_space_after_dot](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_dot)
    ````csharp
    // csharp_space_after_dot = true
    this. Goo();

    // csharp_space_after_dot = false
    this.Goo();
    ````
- [csharp_space_before_dot](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_before_dot)
    
    ````csharp
    // csharp_space_before_dot = true
    this .Goo();

    // csharp_space_before_dot = false
    this.Goo();
    ````
- [csharp_space_after_semicolon_in_for_statement](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_after_semicolon_in_for_statement)
    
    ````csharp
    // csharp_space_after_semicolon_in_for_statement = true
    for (int i = 0; i < x.Length; i++)

    // csharp_space_after_semicolon_in_for_statement = false
    for (int i = 0;i < x.Length;i++)
    ````

- [csharp_space_before_semicolon_in_for_statement](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_before_semicolon_in_for_statement)

    ````csharp
    // csharp_space_before_semicolon_in_for_statement = true
    for (int i = 0 ; i < x.Length ; i++)

    // csharp_space_before_semicolon_in_for_statement = false
    for (int i = 0; i < x.Length; i++)
    ````

- [csharp_space_around_declaration_statements](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_around_declaration_statements)

    ````csharp
    // csharp_space_around_declaration_statements = ignore
    int    x    =    0   ;

    // csharp_space_around_declaration_statements = false
    int x = 0;
    ````

- [csharp_space_before_open_square_brackets](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_before_open_square_brackets)

    ````csharp
    // csharp_space_before_open_square_brackets = true
    int [] numbers = new int [] { 1, 2, 3, 4, 5 };

    // csharp_space_before_open_square_brackets = false
    int[] numbers = new int[] { 1, 2, 3, 4, 5 };
    ````

- [csharp_space_between_empty_square_brackets](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_empty_square_brackets)

    ````csharp
    // csharp_space_between_empty_square_brackets = true
    int[ ] numbers = new int[ ] { 1, 2, 3, 4, 5 };

    // csharp_space_between_empty_square_brackets = false
    int[] numbers = new int[] { 1, 2, 3, 4, 5 };
    ````

- [csharp_space_between_square_brackets](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_space_between_square_brackets)

    ````csharp
    // csharp_space_between_square_brackets = true
    int index = numbers[ 0 ];
    
    // csharp_space_between_square_brackets = false
    int index = numbers[0];
    ````

### Suppression preferences
````csharp
dotnet_remove_unnecessary_suppression_exclusions    = none
````

- [dotnet_remove_unnecessary_suppression_exclusions (IDE0079)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0079#dotnet_remove_unnecessary_suppression_exclusions)
    ````csharp
    using System.Diagnostics.CodeAnalysis;

    class C1
    {
        // 'dotnet_remove_unnecessary_suppression_exclusions = IDE0051'

        // Unnecessary pragma suppression, but not flagged by IDE0079
    #pragma warning disable IDE0051 // IDE0051: Remove unused member
        private int UsedMethod() => 0;
    #pragma warning restore IDE0051

        public int PublicMethod() => UsedMethod();
    }
    ````

### Unnecessary expression preferences
````csharp
csharp_style_unused_value_expression_statement_preference       = discard_variable : silent
visual_basic_style_unused_value_expression_statement_preference = unused_local_variable : silent
````

- [csharp_style_unused_value_assignment_preference (IDE0059)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0059#csharp_style_unused_value_assignment_preference)
    ````csharp
    // csharp_style_unused_value_assignment_preference = discard_variable
    int GetCount(Dictionary<string, int> wordCount, string searchWord)
    {
        _ = wordCount.TryGetValue(searchWord, out var count);
        return count;
    }

    // csharp_style_unused_value_assignment_preference = unused_local_variable
    int GetCount(Dictionary<string, int> wordCount, string searchWord)
    {
        var unused = wordCount.TryGetValue(searchWord, out var count);
        return count;
    }
    ````
- [csharp_style_unused_value_expression_statement_preference (IDE0058)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0058#csharp_style_unused_value_expression_statement_preference)
    ````csharp
    // Original code:
    System.Convert.ToInt32("35");

    // After code fix for IDE0058:

    // csharp_style_unused_value_expression_statement_preference = discard_variable
    _ = System.Convert.ToInt32("35");

    // csharp_style_unused_value_expression_statement_preference = unused_local_variable
    var unused = Convert.ToInt32("35");
    ````
- [visual_basic_style_unused_value_assignment_preference (IDE0059)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0059#visual_basic_style_unused_value_assignment_preference)
    ````csharp
    ' visual_basic_style_unused_value_assignment_preference = unused_local_variable
    Dim unused = Computation()
    ````
- [visual_basic_style_unused_value_expression_statement_preference (IDE0058)](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0058#visual_basic_style_unused_value_expression_statement_preference)
    ````csharp
    ' visual_basic_style_unused_value_expression_statement_preference = unused_local_variable
    Dim unused = Computation()
    ````

### var preferences
````csharp
csharp_style_var_elsewhere              = false : silent
csharp_style_var_for_built_in_types     = false : silent
csharp_style_var_when_type_is_apparent  = false : silent
````

- [csharp_style_var_elsewhere](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0007-ide0008#csharp_style_var_elsewhere)
     ````csharp
    // csharp_style_var_elsewhere = true
    var f = this.Init();
    
    // csharp_style_var_elsewhere = false
    bool f = this.Init();
    ````
- [csharp_style_var_for_built_in_types](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0007-ide0008#csharp_style_var_for_built_in_types)
    ````csharp
    // csharp_style_var_for_built_in_types = true
    var x = 5;
    
    // csharp_style_var_for_built_in_types = false
    int x = 5;
    ````
- [csharp_style_var_when_type_is_apparent](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/ide0007-ide0008#csharp_style_var_when_type_is_apparent)	
    ````csharp
    // csharp_style_var_when_type_is_apparent = true
    var obj = new Customer();
    
    // csharp_style_var_when_type_is_apparent = false
    Customer obj = new Customer();
    ````		

### Wrapping
````csharp
csharp_preserve_single_line_blocks              = true
csharp_preserve_single_line_statements          = false
dotnet_style_operator_placement_when_wrapping   = beginning_of_line
````

- [csharp_preserve_single_line_statements](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_preserve_single_line_statements)
    ````csharp
    //csharp_preserve_single_line_statements = true
    int i = 0; string name = "John";

    //csharp_preserve_single_line_statements = false
    int i = 0;
    string name = "John";
    ````
- [csharp_preserve_single_line_blocks](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/formatting-rules#csharp_preserve_single_line_blocks)
    ````csharp
    //csharp_preserve_single_line_blocks = true
    public int Foo { get; set; }

    //csharp_preserve_single_line_blocks = false
    public int MyProperty
    {
        get; set;
    }
    ````
- [dotnet_style_operator_placement_when_wrapping]()
````csharp
````
