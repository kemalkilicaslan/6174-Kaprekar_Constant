# 6174

![Dattatraya Ramchandra Kaprekar](https://miro.medium.com/v2/resize:fit:348/format:webp/1*BVuqERAkokiSnHkDulHzhA.gif)

## What is 6174?

Firstly, it is **A MYSTERIOUS NUMBER**.

Dattatraya Ramchandra Kaprekar, a genius who loves to play with numbers and describes himself as a number theory enthusiast, announced this mysterious number to the world at a symposium he attended in 1949, even though he did not receive any formal mathematics education.

## Why 6174?

Yes, let's talk about the answer to this question. First of all, let's think of a 4-digit random number with **at least one digit different**. let's call this number 1000, we can also call it 1. Now I can hear you say that the number 1 does not have 4 digits. Yes, it has 4 digits 0 0 0 0 1 yes, this is a number consisting of four digits. After accepting this way. our next process proceeds as follows.

**In the first step** let's pick a random 4-digit number (2791 or 5094 or 3006 or 8000)

I chose 1000 😁.

**In the second step**, let's get the **largest number** and **smallest number** that we can get by changing the **digit values** of the digits of the number we have chosen. For example, I said 1000, the largest number we can get with this number is 1000 and the smallest number is 0001. **0001** yes.

**In the third step**, we will find the difference between the largest number and the smallest number. That is;

**1st operation:** 1000-0001=0999

The next step will be to obtain the largest and smallest number by changing the digit values of the digits of this difference number. And again we will find the difference between them.

**2nd operation:** 9990-0999 =8991

Then,

**3rd operation:** 9981-1899=8082

...

By proceeding in this way, at worst you will reach the number 6174 in **7 operations**, if you are lucky you can reach it in one step, this will depend entirely on the 4-digit number you have chosen.

**4th operation:** 8820-0288=8532

**5th transaction:** 8532-2358=6174

Aaaaaaaaaa!!! 🫢 6174 but how the hell? 🤔 We are partly lucky, we found 6174 before the 7th transaction 😉

Let's take the process one step further.

The largest number we will obtain with 6174 will be **7641** and the smallest number will be **1467**.

**7641-1467=6174**

Yes, now the process enters a vicious circle, no matter how many operations we progress, we cannot get rid of 6174.

That's why it is **A MYSTERIOUS NUMBER**.

Of course, I couldn't stay comfortable, so I said I would write it in Python.

```python
# 6174-Kaprekar_Constant

def kaprekar(num): # We define the Kaprekar function

    if num == 6174: # If the number is 6174, the operation is finished and the result is printed
        print("Result: 6174")
        return

    while num != 6174: # A loop is started which continues until the number is 6174
        digits = [int(d) for d in str(num)] # Separate the digits of the number and assign them to an array

        while len(digits) < 4: # Add a leading zero until the array has 4 digits
            digits.insert(0, 0)

        # New numbers are obtained by ordering the numbers from small to large and from large to small
        ascending = int(''.join(map(str, sorted(digits))))
        descending = int(''.join(map(str, sorted(digits, reverse=True))))
        
        # The difference between the new numbers is calculated and assigned to the variable num for the next iteration
        num = descending - ascending

        # Operation steps and result are printed on the screen
        print(f"{descending:04d} - {ascending:04d} = {num:04d}")

kaprekar(1000) # You can write 1, you can write 60, maybe 803, maybe 4795...
```

The output is as follows,

```
1000 - 0001 = 0999
9990 - 0999 = 8991
9981 - 1899 = 8082
8820 - 0288 = 8532
8532 - 2358 = 6174
```

According to these operations, the number 495 in 3-digit digits is mysterious...

or see the code here. 😊

```python
def kaprekar(num):

    if num == 495:
        print("Result: 495")
        return

    while num != 495:        
        digits = [int(d) for d in str(num)]

        while len(digits) < 3:
            digits.insert(0, 0)

        ascending = int(''.join(map(str, sorted(digits))))
        descending = int(''.join(map(str, sorted(digits, reverse=True))))
        num = descending - ascending

        print(f"{descending:03d} - {ascending:03d} = {num:03d}")

kaprekar(8) # I tried 8.
```

the output is as follows,

```
800–008 = 792
972–279 = 693
963–369 = 594
954–459 = 495
```

5 and 6 maybe there are other digits, who knows...