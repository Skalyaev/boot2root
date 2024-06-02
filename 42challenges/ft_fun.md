# ft_fun

```bash
cd ft_fun
ls -S -lA
```
```
total 3052
-rw-r----- 1 skalya skalya 32096 13 août   2015 BJPCP.pcap
-rw-r----- 1 skalya skalya    44 13 août   2015 08GIC.pcap
-rw-r----- 1 skalya skalya    44 13 août   2015 0B2GJ.pcap
-rw-r----- 1 skalya skalya    44 13 août   2015 0D70A.pcap
-rw-r----- 1 skalya skalya    44 13 août   2015 0K842.pcap
...
-rw-r----- 1 skalya skalya    11 13 août   2015 UKFW1.pcap
-rw-r----- 1 skalya skalya    10 13 août   2015 BNFBP.pcap
-rw-r----- 1 skalya skalya    10 13 août   2015 FXG1L.pcap
-rw-r----- 1 skalya skalya    10 13 août   2015 SK03K.pcap
```

These are not real pcap files, and most of hit contain trash

After cleaning `BJPCP.pcap`, here is the content:
```c
char getme8() {
    return 'w';
}
char getme9() {
    return 'n';
}
char getme10() {
    return 'a';
}
char getme11() {
    return 'g';
}
char getme12()
{
    return 'e';
}
int main() {
    printf("M");
    printf("Y");
    printf(" ");
    printf("P");
    printf("A");
    printf("S");
    printf("S");
    printf("W");
    printf("O");
    printf("R");
    printf("D");
    printf(" ");
    printf("I");
    printf("S");
    printf(":");
    printf(" ");
    printf("%c",getme1());  // ?
    printf("%c",getme2());  // ?
    printf("%c",getme3());  // ?
    printf("%c",getme4());  // ?
    printf("%c",getme5());  // ?
    printf("%c",getme6());  // ?
    printf("%c",getme7());  // ?
    printf("%c",getme8());  // w
    printf("%c",getme9());  // n
    printf("%c",getme10()); // a
    printf("%c",getme11()); // g
    printf("%c",getme12()); // e
    printf("\n");
    printf("Now SHA-256 it and submit");
}
//file750
```

```bash
mv BJPCP.pcap main.c
cat *.pcap
```
```
void useless() {
//file265}void useless() {
//file82    printf("Hahahaha Got you!!!\n");
//file142}void useless() {
//file302/*
...
//file235   printf("Hahahaha Got you!!!\n");
//file530   printf("Hahahaha Got you!!!\n");
//file722char getme6() {
...
//file578}void useless() {
//file317}void useless() {
//file161   return 'e';
...
//file593}void useless() {
//file363   printf("Hahahaha Got you!!!\n");
//file3 return 'h';
//file38}void useless() {
//file687
```

Most of files contain trash, so:
```bash
grep -C 100 getme *.pcap
```
```
0T16C.pcap:char getme4() {
0T16C.pcap-
0T16C.pcap-//file115
--
32O0M.pcap:char getme7() {
32O0M.pcap-
32O0M.pcap-//file736
--
331ZU.pcap:char getme1() {
331ZU.pcap-
331ZU.pcap-//file5
--
4KAOH.pcap:char getme5() {
4KAOH.pcap-
4KAOH.pcap-//file368
--
91CD0.pcap:char getme6() {
91CD0.pcap-
91CD0.pcap-//file521
--
B62N4.pcap:char getme3() {
B62N4.pcap-
B62N4.pcap-//file56
--
G7Y8I.pcap:char getme2() {
G7Y8I.pcap-
G7Y8I.pcap-//file37
```

```bash
grep -C 100 return *.pcap
```
```
7DT5Q.pcap: return 'a';
7DT5Q.pcap-
7DT5Q.pcap-//file116
--
APM1E.pcap: return 'I';
APM1E.pcap-
APM1E.pcap-//file6
--
ECOW1.pcap: return 'e';
ECOW1.pcap-
ECOW1.pcap-//file57
--
J5LKW.pcap: return 't';
J5LKW.pcap-
J5LKW.pcap-//file522
--
T44J5.pcap: return 'p';
T44J5.pcap-
T44J5.pcap-//file737
--
T7VV0.pcap: return 'r';
T7VV0.pcap-
T7VV0.pcap-//file369
--
ZPY1Q.pcap: return 'h';
ZPY1Q.pcap-
ZPY1Q.pcap-//file38
```

Now we got to match each `return` with its `getme` function

We can see that each `getme()` function is a '//file` number

We notice that for each number `n` of `getme` files, there is a corresponding `return` file that is actually `n+1`:

```
331ZU.pcap:char getme1() {
331ZU.pcap-
331ZU.pcap-//file5
--
APM1E.pcap: return 'I';
APM1E.pcap-
APM1E.pcap-//file6
```

```
G7Y8I.pcap:char getme2() {
G7Y8I.pcap-
G7Y8I.pcap-//file37
--
ZPY1Q.pcap: return 'h';
ZPY1Q.pcap-
ZPY1Q.pcap-//file38
```

```
B62N4.pcap:char getme3() {
B62N4.pcap-
B62N4.pcap-//file56
--
ECOW1.pcap: return 'e';
ECOW1.pcap-
ECOW1.pcap-//file57
```

```
0T16C.pcap:char getme4() {
0T16C.pcap-
0T16C.pcap-//file115
--
7DT5Q.pcap: return 'a';
7DT5Q.pcap-
7DT5Q.pcap-//file116
```

```
4KAOH.pcap:char getme5() {
4KAOH.pcap-
4KAOH.pcap-//file368
--
T7VV0.pcap: return 'r';
T7VV0.pcap-
T7VV0.pcap-//file369
```

```
91CD0.pcap:char getme6() {
91CD0.pcap-
91CD0.pcap-//file521
--
J5LKW.pcap: return 't';
J5LKW.pcap-
J5LKW.pcap-//file522
```

```
32O0M.pcap:char getme7() {
32O0M.pcap-
32O0M.pcap-//file736
--
T44J5.pcap: return 'p';
T44J5.pcap-
T44J5.pcap-//file737
```

So:
```c
int main() {
    printf("M");
    printf("Y");
    printf(" ");
    printf("P");
    printf("A");
    printf("S");
    printf("S");
    printf("W");
    printf("O");
    printf("R");
    printf("D");
    printf(" ");
    printf("I");
    printf("S");
    printf(":");
    printf(" ");
    printf("%c",getme1());  // I
    printf("%c",getme2());  // h
    printf("%c",getme3());  // e
    printf("%c",getme4());  // a
    printf("%c",getme5());  // r
    printf("%c",getme6());  // t
    printf("%c",getme7());  // p
    printf("%c",getme8());  // w
    printf("%c",getme9());  // n
    printf("%c",getme10()); // a
    printf("%c",getme11()); // g
    printf("%c",getme12()); // e
    printf("\n");
    printf("Now SHA-256 it and submit");
}
```
