# Algorithm to calculate any weekday

This is a cool trick that needs a little bit of mental gymnastics and regular training. The formula I use is quite simple and is often used in other ressources to show people how to determine rapidly the weekday of any given date. 

Before introducing it, the definition of a leap year should be recalled. A year is a leap year if it can be divided by $4$. However, there are years such as $2100$ that can be divided by $4$ but are not leap. The second condition is that if a year can be divided by $100$ (centurial years such as $1700$,$1900$,$2100$, etc...), for it to be leap, it must be divisible by $400$.

The equation to calculate a weekday is the following one:

$$
\begin{equation}
D = (I_{d}+I_{m}+I_{y}) \mod{} 7
\end{equation}
$$

$\mod{} 7$ means the final result is the remainder of a division by 7.

The different variables are:
* $D$ : the weekday index. For Sunday, $D=0$. For Monday, $D=1$,$\dots$, and for Saturday, $D=6$.
* $I_{d}$ : the month's day index. For the 4th of june, $I_{d}=4$
* $I_{m}$ : the month index. This number is more complicated and is dependant sometime (January and February) of the year being leap or not. The table, a few paragraphs below, summarizes the indices corresponding to each month. You can see that the indices for January and February are substracted by one for leap years.
* $I_{y}$ : the year index, which can take the values $\{0,1,2,3,4,5,6\}$. Using $d$ as the last two digits of the year (for $y=1992$, $d=92$), we can determine this index with:
$$
\begin{equation}
I_{y}= (d+\lfloor \frac{d}{4} \rfloor + I_{c}) \mod{} 7
\end{equation}
$$

$I_{c}$ is an index that depends that depends on the century. Since the Gregorian calender is cyclic with a period of $400$ years, you only need to know four indices to get the correct date. Those indices are $I_{1800} = 3$, $I_{1900}=1$, $I_{2000}=0$ and $I_{2100}=5$. But you must careful if the centurial year you're considering is a leap year. 

For instance, you would assume that $y=2200$ has the same index as $y=1800$ but that's not true. Indeed, calculating first the index for $y=2199$:

$$
I_{2199} = (99+\lfloor \frac{99}{4} \rfloor+5)\mod{} 7=(99+24+5)\mod{} 7= 128 \mod{} 7 = 2
$$

To get the index of the following year, you just increment by $1$, but since $y=2200$ is also a leap year, you should increment again by $1$. Therefore $I_{2200}=4\neq I_{1800}$. It's also becomes easier if you remember that $(99+\lfloor \frac{99}{4} \rfloor)\mod{} 7=4$, then you can just add the year index of the previous year modulo 7. As an exercice, we can calculate $I_{1600}$ and $I_{2300}$.

$y=1600$ is obviously a leap year and is exactly $400$ years apart from $2000$, meaning that $04/01/1600$ and $04/01/2000$ fall both on a saturday. Since both years are leap, it means that $I_{1600}=I_{2000}=0$.

$y=2300$ is not a leap year and is exactly $400$ years apart from $1900$. Do they have the same index? We know from the previous example that $I_{2200}=4$, thus $I_{2300}=(4+4+1)\mod{} 7=2\neq I_{1900}$. You see how difficult it can be to get the correct index, even with the cyclicity argument.

| Index |  0  |              1             |                    2                   |   3  |          4         |             5            |               6              |
|:-----:|:---:|:--------------------------:|:--------------------------------------:|:----:|:------------------:|:------------------------:|:----------------------------:|
| Month | May | LY February, August | CY February, March, November  | June | September, December | LY January, April, July | CY January, October |

Here LY means Leap Year and CY means Common Year.

Overall this method is not so hard, but it really needs some practice. With time, you will learn by heart indices and get much faster. Other methods exist to compute the weekday such as the Doomsday rule or the Zeller congruence. I don't know any one of them that don't require at least some memorization.


## Application examples

* 02/02/2024 : $I_{d} = 2$, $I_{m}=1$, $I_{2024}=(24+\lfloor \frac{24}{4} \rfloor+0)\mod{} 7 = (24+6+0)\mod{} 7 = 2$. Thus, $D=(2+1+2)\mod{} 7 = 5$ (Friday)

* 08/06/1945 : $I_{d} = 6$, $I_{m}=1$, $I_{1945}=(45+\lfloor \frac{45}{4} \rfloor+1)\mod{} 7 = (45+11+1)\mod{} 7 = 1$. Thus, $D=(6+1+1)\mod{} 7 = 1$ (Monday)

* 01/24/1878 : $I_{d} = 24$, $I_{m}=6$, $I_{1878}=(78+\lfloor \frac{78}{4} \rfloor+3)\mod{} 7 = (78+19+3)\mod{} 7 = 2$. Thus, $D=(24+6+2)\mod{} 7 = 4$ (Thursday)

* 09/17/2017 : $I_{d} = 17$, $I_{m}=4$, $I_{2017}=(17+\lfloor \frac{17}{4} \rfloor+1)\mod{} 7 = (17+4+0)\mod{} 7 = 0$. Thus, $D=(17+4+0)\mod{} 7 = 0$ (Sunday)

* 12/31/2106 : $I_{d} = 31$, $I_{m}=4$, $I_{2106}=(6+\lfloor \frac{6}{4} \rfloor+5)\mod{} 7 = (6+1+5)\mod{} 7 = 5$. Thus, $D=(31+4+5)\mod{} 7 = 5$ (Friday)


