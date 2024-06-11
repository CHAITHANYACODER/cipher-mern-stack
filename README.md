/*
    -----Functions and Objects-----
*/
function test_function_and_objects(){
    function sum(a, b){             // Defining a function "sum()"
        return a+b
    };

    console.log(sum(10, 20));                    // calling the function

    sum.message = "Hello World";    // initiating an object with a member "Message"
    console.log(sum.message);
};




/*
    -----Working with objects-----
*/
function test_objects(){
    let account = {};           // declaring an empty object
    account.role = "member";    // initiate a member of the object
    let account_permission = {
        admin : "admin",
        member : "member",
        guest : "guest"
    };
    account.permission = account_permission[account.role] || "No permissions";     // initiate a member "permission", which defaults to "no permission"
    console.log(account.permission);
};




/*
    -----Deconstruction-----
*/
// initiate an object with the keys "name", "age" and "gender"
function test_deconstruction(){
    user = {
        name : "John",
        age : "20",
        gender : "Male"
    }


    let {age: user_age, gender} = user;     // from object "user", deconstruct age as "user_age" and deconstruct gender
    console.log("User_age: " + user_age + "\t gender: " + gender);          // output user_age and gender to the console

    let numbers = [1, 2, 3];
    let [a, b, c] = numbers;                   // from array "numbers", deconstruct the elements in order as "a", "b", and "c"
    console.log("a: " + a + "\tb: " + b + "\tc: " + c);               // output a, b and c to the console
};



/*
    -----Deconstruction and functions with default values-----
*/
function test_deconstruction_and_functions(){
    function func_1(fuelcapacity = 1000, fuelconsumption = 10)              // A function with 2 paramters with their pre-defined default values
    {console.log(fuelcapacity + "\t" + fuelconsumption);};

    function func_2({fuelcapacity = 1000, fuelconsumption = 10})            // A function with an object as a parameter, and the order of the members in the object does not matter
    {console.log(fuelcapacity + "\t" + fuelconsumption);};

    function func_3({fuelcapacity = 1000, fuelconsumption = 10} = {})       // Simplification: (obj = {}), where an empty object "{}" is taken as a default value
    {console.log(fuelcapacity + "\t" + fuelconsumption);};

    // calling the functions
    func_1();
    func_1(10, 1);
    func_2({fuelconsumption : 2, fuelcapacity : 200});
    func_2({});
    func_3();
};
