
To generate random numbers, the property of time is important. Since the value of time is not static and it's continuously changed.
First we take two variables 1 and 10 which is also the range of the random generated numbers.
These two numbers are passed in generate() method, it's the main method where the output value received.
generate() method calls the validate_inputs(), where the value of multiplier and seeds are got, these are the random values.
in get_seeds() method:
 value_1, value_2 = int(str(time() - int(time()))[-1]), int(str(time() - int(time()))[-2])
is used to generate the any random value
Here: e.g. time() = 1507049023.53
int(time()) = 1507049023(only int value)
basically str(time() - int(time())) has only the decimal value 
& int(str(time() - int(time()))[-1]), int(str(time() - int(time()))[-2]) give the last and second last value of the decimal, use as the random values 
in validate_inputs() :
  above these two random values are used as multiplier, seed
  in the while loop, basically we are getting all values2(seed) which are in the range of 1 < value < 10 and same for value1(multiplier), in [1,     3, 7, 9]
 
in generate() method :
we gets these two values, which are further used to generate random numbers,
current_iteration = (current_iteration * multiplier) + increment
and to get values only in the range of modulus (10 in our case), we use:
 if current_iteration > modulus:
                current_iteration %= modulus
all the random values are append in output.append(current_iteration)

To get all values we join it with ' ' (null), all values are combined now:
str(''.join([str(i) for i in output])

and we return the last value of the string result = int(str(''.join([str(i) for i in output]))[-1])
this is first random value within range of 1 to 10 

now, to add into list1
we check its value, if it's length <= 5 and list1 length <= 27, because we are storing only 27 values which are <= 5
same, to add into list2
if values are >= 5 and length of the list2 is <= 73, we add this value into list2

Now in the end when these two lists have its required length 27 and 73 consequently, we stop the loop by setting "loop=False"

So in the end, we find two lists with the length of 27 and 73, which have values <= 5 and >= 5 consequently.
