---
layout: project
location: "../.."
main_title: SCLS Foundation Core
scls_foundation_version: "0.1"
---
<h1>SCLS Foundamental Core</h1>
<h2>Presentation</h2>
<section>
    SCLS Foundamental Core contains each very basics functions to use SCLS Foundamental, or that can be used in a C++ program.
    It has a lot of differents features, presented here.
    They are quite different and not linked, but they are cool as well.
</section>
<h2>
    Debugging helper
</h2>
<section>
    <article>
        SCLS Foundamental Core offers a little debugging tool, using "std::cout" to create a debugging output with the "print" function.
        The difference with a simple "std::cout" is the ability to target a special debugging.
        Indeed, to print datas, you should specify two things : the type and the sender of the data.
        Theses two things aren't subjects to any kinds of nomenclature, you can do literaly how you want.
        You can then tell SCLS Foundamental Core which type / sender can or cannot be printed, to target a part of the program to debug.
        To be more precise, the "print" function print the type, the sender, and the message, each separate by a editable std::string separation.
        You can also disable each "print" functions if you want.
        As the authorized sender and type are stored in vector (see <a href="authorized_sender">authorized_sender()</a> and <a href="authorized_type">authorized_type()</a>), you can use this functions and base vecor functions to handle the authorisation.
        For exemple, use "scls::authorized_type().clear()" to clear the authorisation, and "scls::authorized_type().push_back("Test")" to add some other.
        To do a quite big exemple, assuming you are developing a Mandelbrot set creator with an image, you may create two classes : "Complex" and "Mandelbrot_Creator".
        If your result is not what you are expecting, you can place some "print" functions, the one in the "Complex" class with the type "Complex", and the other one in the "Mandelbrot_Creator" class with the type "Mandelbrot_Creator".
        Then, you can tell SCLS Foundamental Core which type can or not be printed to see which part of the program is doing unexpected behaviors.
        You can do the same thing with the sender of the data.
    </article>
    <h3>
        Functions
    </h3>
    <article>
        The functions are documented in alphabetical order, which may not be their place in the code.
        <h4 href="#authorized_sender">
            std::vector&lt;std::string&gt;& authorized_sender()
        </h4>
        <div>
            Return a reference towards authorized sender to be printed by the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4 href="#authorized_type">
            std::vector&lt;std::string&gt;& authorized_type()
        </h4>
        <div>
            Return a reference towards authorized type to be printed by the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            bool can_print()
        </h4>
        <div>
            Return if the print function can be used or not, if it is enable or not.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            bool is_sender_authorized(std::string sender_to_test)
        </h4>
        <div>
            Return if the sender "sender_to_test" is authorized to be printed by the "print" function.<br>
            IMPORTANT : if "_authorized_sender" is empty, this function will always return true.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            bool is_type_authorized(std::string type_to_test)
        </h4>
        <div>
            Return if the type "type_to_test" is authorized to be printed by the "print" function.<br>
            IMPORTANT : if "_authorized_type" is empty, this function will always return true.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            template &lt;typename Type_To_Print = std::string&gt;<br>
            void print(std::string type, std::string sender, Type_To_Print message)
        </h4>
        <div>
            Print the message "message" to the console, with the type "type" and the sender "sender".<br>
            The use of a typename allows the user to print any type of data, if their "&lt;&lt;" insertion operator is overloaded.
            For more details, see <a href="https://www.geeksforgeeks.org/overloading-stream-insertion-operators-c/" target = "_blank">this geeksforgeeks article</a>.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string sender_message_separation()
        </h4>
        <div>
            Return the separation between the sender and the message in the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            void set_can_print(bool new_can_print)
        </h4>
        <div>
            Change if the print function can be used or not, if it is enable or not, by "new_can_print".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            void set_sender_message_separation(std::string new_sender_message_separation)
        </h4>
        <div>
            Change the separation between the sender and the message in the "print" function by "new_sender_message_separation".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            void set_type_sender_separation(std::string new_type_sender_separation)
        </h4>
        <div>
            Change the separation between the type and the sender in the "print" function by "new_type_sender_separation".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string type_sender_separation()
        </h4>
        <div>
            return the separation between the type and the sender in the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
    </article>
    <h3>
        Hiddens things
    </h3>
    <article>
        <h4>
            static std::vector&lt;std::string&gt; _authorized_sender
        </h4>
        <div>
            Vector storing each authorized sender to be printed by the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            static std::vector&lt;std::string&gt; _authorized_type
        </h4>
        <div>
            Vector storing each authorized type to be printed by the "print" function.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            static bool _can_print
        </h4>
        <div>
            Variable storing if the "print" function is enable or not, by default to true.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            static std::string _sender_message_separation
        </h4>
        <div>
            Variable storing the separation between the sender and the message in the "print" function, by default to " : ".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            static std::string _type_sender_separation
        </h4>
        <div>
            Variable storing the separation between the type and the sender in the "print" function, by default to " :-> ".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
    </article>
</section>
<h2>
    Datas structures manipulation
</h2>
<section>
    <article>
        SCLS Foundamental offers some usefull functions to manipulate some data structure, like std::string, std::vector, or char*.<br>
        There are in SCLS Foundamental some little usefull functions to do some simple std::string manipulation.
        You can check if an another std::string appears in a std::string with "contains", to count its number of occurence with "count", split a std::string with "cut_string" or join it with "join_string".
        You can also put an entire std::string to lowercase with "lowercase_string", replace a part of a std::string by an another std::string in "replace", convert a std::string to utf_8 with "to_utf_8" and convert a char array to a std::string with "char_array_to_string".
        However, if you aspire to use the "to_utf_8" function, read the documentation below before.<br>
        There are also some others usefull functions, like "swap_vector" which can swap a vector, or "swap_char_array" which san swap a char array.<br>
        If you want to convert a std::string to a double, the std library gives the "std::stod" function.
        But, with this function, in some computer, the separation between the integer part and the decimal is ".", and in others computer, it's ",".
        To be the most portable possible, SCLS Foundamental offers a function "string_to_double(std::string str)" which takes this in count to convert the std::string.
        It tests which character to use and which not to use, and replace it if necessary for the conversion.
    </article>
    <h3>
        Functions
    </h3>
    <article>
        <h4>
            std::string char_array_to_string(char* c_a, unsigned int c_a_size)
        </h4>
        <div>
            Convert the char array "c_a" of size "c_a_size" to a std::string and return it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            bool contains(std::string str, std::string part)
        </h4>
        <div>
            Return if the std::string "str" contains at least one occurence of "part" in it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            template&lt;typename T&gt;
            bool contains(std::vector&lt;T&gt; vec, T element)
        </h4>
        <div>
            Returns if the std::vector "vec" contains the element "T".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            unsigned int count(std::string str, std::string part)
        </h4>
        <div>
            Return the number of occurrence of the std::string "part" in the std::string "str".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            template&lt;typename T&gt;
            unsigned int count(std::vector&lt;T&gt; vec, T element)
        </h4>
        <div>
            Return the number of occurrence of "T" in the std::vector "vec".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::vector&lt;std::string&gt; cut_string(std::string string, std::string cut, bool erase_blank = false, bool erase_last_if_blank = true)
        </h4>
        <div>
            Split the std::string "string" at each "cut" occurrence in "string", and return it in a std::vector.<br>
            If "erase_blank" is true, each empty part cutted are deleted.<br>
            If "erase_last_if_blank" is false and the last part of "string" is exactly "cut", the function adds an empty std::string in the returned std::vector.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string lowercase_string(std::string str)
        </h4>
        <div>
            Put the entire std::string "str" to lowercase and return it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string join_string(std::vector&lt;std::string&gt; strings, std::string separation = "")
        </h4>
        <div>
            Join each std::string in the std::vector "strings", separate by "separation", in a single std::string, and return it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string replace(std::string str, std::string to_replace, std::string new_str)
        </h4>
        <div>
            Replace in the std::string "str" the occurences "to_replace" by the std::string "new_str" and return it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            double string_to_double(std::string str)
        </h4>
        <div>
            Convert the std::string "str" to a double, by considering "_float_character" and "_non_float_character".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            void swap_char_array(char* array, unsigned int size)
        </h4>
        <div>
            Swap the char array "array" of size "size". As the char array is a pointer, there is no needs to return it, as it is directly swapped.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            template&lt;typename T&gt;
            std::vector&lt;T&gt; swap_vector(std::vector&lt;T&gt; v)
        </h4>
        <div>
            Swap the vector "v" of any type "T", and return it swapped.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string to_utf_8(const char* character, unsigned int text_size)
        </h4>
        <div>
            Return a std::string in UTF-8, coming from a char array "character" of size "text_size" not already converted.<br>
            IMPORTANT : during the test phase, multiples unexpected behaviors have been found. You should do some test to see if your compiler do not already use UTF-8 before using this function. Moreover, the console can't print properly a lot of characters, so using the scls::Image "text_image" function may be more appropriate to test it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            std::string to_utf_8(std::string str)
        </h4>
        <div>
            Return a std::string in UTF-8, coming form a std::string "str".<br>
            IMPORTANT : during the test phase, multiples unexpected behaviors have been found. You should do some test to see if your compiler do not already use UTF-8 before using this function. Moreover, the console can't print properly a lot of characters, so using the scls::Image "text_image" function may be more appropriate to test it.<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
    </article>
    <h3>
        Hiddens things
    </h3>
    <article>
        <h4>
            static std::string _float_character
        </h4>
        <div>
            Separation between the integer and decimal part in a std::string double, by defaults to "".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            static std::string _non_float_character
        </h4>
        <div>
            Other possible separation between the integer and decimal part in a std::string double, but not in this computer, by defaults to "".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
        <h4>
            void _test_separation_character()
        </h4>
        <div>
            Test and assign "_float_character" and "_non_float_character", to know which ones is "." and which one is ",".<br>
            This function was added in the version 0.1 and last edited in the version 0.1.
        </div>
    </article>
</section>
<h2>
    Code specification
</h2>
<section>
    This file define the macro "SCLS_FOUNDATION_CORE".
</section>