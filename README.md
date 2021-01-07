# C++
## The process of learning and side project  
## Author: DONG GUAN-CHENG (董貫程)
#### ***程式語言簡介***
機器語言->組合語言(組譯器，需利用指令集來規劃程式)->編譯語言(編譯器，速度快)->直譯語言(一行一行翻譯，速度較編譯語言慢)  

C++語言是由原本的C語言所發站出來的程式語言。由於當時有發展大型軟體的需要，所以引入物件導向的觀念，被引入C語言中，並有了C with Classes的觀念，最後改成為C++。而C++與C語言相容  

``物件導向設計``是以系統所要處理的物件，作為系統架構的出發點，會先從抽象的層面來分析要處理的類別(Class）的資料，然後思考各種類別的資料，會以哪些方法(Method)來操作，然後最後使用繼承來表現其共同點。而整個系統是由各個封裝良好的物件模組所架構起來，每一個物件模組就是一個類別定義。它包含一組私有的資料結構，以及開放給外部操作這組資料的方法，以``模組化``為基本精神，用封裝、繼承、多型...等方式為原則，來產生具有可重用性、可維護性以及可擴展性的軟體
***
#### ***資料資料型別與計算***
* ***C++程式架構***  
#include <iostream> //插入標頭檔  
 using namespace std; //為使用新型的標頭檔，使用命名空間std中的函式  
所有變數都必須先宣告其變數型態  
加入註解有兩種方式1. 「//」之後 2. 放置在「/*」和「*/」之間  
 
* ***變數的宣告與使用***  
int, char, float等資料型態，變數在電腦中是一個佔有記憶體空間的資料存放區，將資料的記憶體位址以變數的觀念取代，若要存取資料，則以該變數名稱來指定即可存取資料，可將其看作記憶體中存放未知數值的記憶體空間。  
也可用於宣告自定義函數變數宣告方式:  
``**type var-name**`` 其中``type``為變數資料型態，``VAR-NAME``變數名稱須符合變數命名規則
``;``號為告知編譯器此行程式到此結束，變數一般在程式區塊最上方  

* ***整數型態-int, short,long***  
long型態-使用記憶體空間最大，需要``4個位元組(bytes)``記憶體空間，1byte=8bit(位元)，每個位元儲存0和1的狀態  
short型態-需要``2bytes``記憶體空間來儲存  
int型態-較為特殊，在早期16位元系統下(DOS)用``2bytes``儲存，32或64作業系統下用``4bytes``記憶體空間來儲存  
電腦儲存整書方式式使用2的補數，二進位位元來表示在某一段範圍內的整數 ex:011->3 101->-3  

* ***浮點數型態***  
浮點數其實就是小數，所需記憶體數量比整數大，``單精度float``需要``4 bytes``來儲存，``雙精度float``需要``8 bytes``來儲存  

* ***字元型態***  
只需要``一個byte``的記憶體空間來儲存就好，可以利用char來儲存單一個字元  

* ***無值-void**  
內涵虛無或沒有的概念  
ex:int rand(void);->沒有引數但有整數傳回值  

* ***布林型態-boolean**  
作為C++的資料型別時，只有(True 或 1)和(False 或 0)，只需要1個byte的記憶體空間來儲存即可  
```
布林宣告方式
bool var-name;
OR  
bool check=true; //指定布林變數初值為true
```
* ***常數與前置處理器 #define ***  
常數與變數的區別，常數無法進行修改值，變數可以被指定或更改
宣告方式:``const type var-name;``，另外可以使用``#define``開頭的前置處理器  
來變換常數或字串的自訂識別名稱(切記不可加上分號) 語法:``#define 識別子 常數(字串)``->當有變動時可以不需到程式碼裡面更動每一個用到識別子的地方

* ***輸出與輸入***  
使用者輸入資訊，而程式顯示執行的結果。在C++裡面必須使用定義標準輸出／輸入的iostream library ，因此只要在程式中需要輸入輸出，就要在程式開頭加上``#include <iostream>``另外，由於 (cout輸出函式) 和 (cin輸入函式) 都是定義在「std」命名空間中，要記得使用using 指令來宣告要使用的命名空間，會再開頭加上「using namespace std;」指令  
``
cin>>x>>y;  //將使用者輸入的兩數字依序存入變數x和y中
cout<<"hello"<<endl<<x<<endl;  //可以連續輸出

ps:可以在cout輸出函式加上控制字元，來控制輸出的呈現效果:\0->空格,\b->倒退,\t->移到下一定位點,\n->插入新行,\"->插入雙引號,\'->插入單引號,\\->插入反斜線
``

***
#### ***運算子、運算式與敘述***  
* ***指定運算子***  
assignment operator符號是等號"=",會把等號右方的值(變數或運算式)，指定給等號左方的變數
ex:int i=0; i=i+1; 

* ***算數運算子***  
『+』,『-』,『*』,『/』(取商數),『%』(取餘數)  
int a=10;e=a/4; ans=2 而不是2.5 因為變數a式整數型態所以會得到2  

* ***關係運算子***  
為比較關係的運算，可能為`‵True(真)->非零的值‵`或為``False(偽)->零值``，通常用於程式流程控制  
『> 大於,< 小於,>= 大於等於, <= 小於等於, == 等於(比較), != 不等於』  
 ex: int a=5,b; b=(a==5); ans:b值等於1  
 
* ***邏輯運算子***  
『&&』是邏輯符號AND, 『||』是邏輯符號OR, 『!』是邏輯符號NOT  

* ***遞增與遞減運算子***  
『++』->遞增運算子, 『--』->遞減運算子 將所運算的變數值進行加1或者是減1  
優點為:在電腦中提供比較低階的運算，執行效率較佳  
ex: a++的意義是，先將變數a的值取出使用，結束後再將變數a值加1,++a的意義是，先將變數a加上1之後取出其數值    

* ***運算子優先運算順序***  
1. () 2. !,-(算數運算子的負號),++,-- 3.*,/,% 4.+,- 5.<<,>>,>>> 6.>,>=,<,<= 7.==,!= 8.&(位元AND) 9.^(位元XOR) 10.|(位元OR) 11.&&(邏輯AND) 12.||(邏輯OR) 13.？:(條件控制運算，由右至左) 14.=,op=(指定運算子，由右至左)  

* ***資料型態的轉換***  
可以進行強制資料型態轉換。將整數型態變數轉換為浮點數型態，在儲存到浮點數變數  
語法:``(type)variable;``  
ex:{  
int a,b;  
float c;  
a=7;  
b=2;  
c=(float)a/b;  
printf("%f",c);  
}  ans:3.50000 假若沒加(float)則會顯示3.0000  

* ***逗點運算子***  
將運算式接再一起，用於宣告多個變數時
ex: int i, j, k;  

* ***運算式與敘述***  
所謂的運算式(expression):就是由運算子(operator ex:=,+...)或運算元(operand)組合而成，運算子有前面所提的算術、邏輯、指定...等等;而運算元可以是常數、變數或是函數皆可  
statement:指的是完整的指令，用分號來做結尾  
program:是許多有意義的敘述所組成  

***
#### ***流程圖與選擇性敘述***  

algorithm定義為->為解決某一問題或完成特定工作，一系列有次序且明確的指令集合  
包含 輸入、輸出、明確性、有限性、有效性。對於複雜演算法用流程圖更能了解整個流程，方便進行修改、維護及除錯，並且可增加程式的可讀性  

* ***判斷結構if敘述***  
用於判斷是否進入程式區塊，條件式成立，則會進入程式區塊;如果條件不成立，則會進入if敘述之後的其他敘述  
語法:  
```  
if(條件式){  
程式區塊;}  
```  

* ***判斷結構if...else...敘述***  
會根據條件式的真偽，決定要進入的程式區塊為何，成立執行程式區塊1，不成立執行程式區塊2  
語法:  
```  
if(條件式){  
程式區塊1;}  
else {  
程式區塊2;}  
```  

* ***判斷結構if...else if...else...敘述***  
此敘述提供了多種狀況的選擇判斷  
語法:  
```  
if(條件式1){  
程式區塊1;  
}  
else if(條件式2){  
程式區塊2;  
}  
else if(條件式N){  
程式區塊N;  
}  else{  
程式區塊N+1;  
}  
```  

* ***判斷結構之巢狀if***  
當if敘述包含其他if敘述時，稱此種if敘述為巢狀if  
語法:  
```  
if(條件式1){   
 if(條件式2){  
 程式區塊1;
 }  
 else {  
 程式區塊2;  
 }  
else {  
 if(條件式3){  
 程式區塊3;
 }  
 else{  
 程式區塊4;  
 }  
}  
```  

* ***判斷結構之switch敘述***  
為何將多選一的情況簡化，還提供了switch敘述，switch會根據某一個``字元``或是``整數變數``，來判斷要進入哪一個程式碼區塊，直到遇到break敘述，再跳出switch的程式區塊;如果沒有值符合，會進入default之後的程式區塊，有時也可以不寫default，直接跳出switch區塊  
語法:  
```  
switch(變數或運算式){  
case 值1:  
程式區塊1;  
break;  
case 值2:  
程式區塊;  
break;  
...  
case 值N:  
程式區塊N;  
break;  
default:  
程式區塊N+1;  
}  
```  

***  
#### ***迴圈***
* ***迴圈結構之for敘述***  
迴圈結構又稱為重複性結構，通常在``明確知道要執行迴圈的次數``時，會使用for迴圈來設計，使用左右大括號來含括敘述，如只有一行程式敘述時，可省略大括號  
語法:  
```  
for(起始式;判斷式;運算式)  
{  
程式區塊;  
}  
```  
起始式:初始化一個或多個變數的值  
判斷式:藉此判斷是否進入程式區塊  
運算式:對變數做一些運算  
ex: for(i=0;i<5;i++)  
printf("%d",i);  
ps:起始式、判斷式、運算式都可以為空白，但是中間分號仍然要寫出來，否則會造成語法錯誤  

* ***迴圈結構之while敘述***  
結構與for迴圈相似，但是沒有起始式與運算式的區塊，而是把起始式和運算式所需要的計算，放到while迴圈的前面或迴圈內  
語法:  
```  
while(判斷式){  
程式區塊;  
}  
```  
ex:  
i=0; //起始式  
while(i<5){  //判斷式  
printf("%d",i);  
i++;  //運算式  
}  

* ***迴圈結構之do...while敘述***  
do...while為while迴圈的變形，差別在於迴圈內的敘述會先執行一次，執行一次後再根據判斷式的真偽，決定是否再進入迴圈之中  
語法:  
```  
do{  
程式區塊;  
} while(判斷式);  
```

* ***Continue敘述***  
一般迴圈的執行流程都是在程式區塊執行完畢後，才繼續下一輪。某些特殊情況，需略過接下來的程式碼，然後直接跳到下一輪的起始位置
此時就可用cintinue敘述，通常搭配判斷結構，如if敘述  
語法:  
```  
for(i=0;i<=10;i++){  
> if(i%2)  
>> continue;  
> total=total+i;  
}  
```

* ***break敘述***  
break敘述雨continue敘述剛好相反，程式遇到break時，將會直接跳出迴圈，不再執行迴圈內的敘述，  
語法:  
```  
for(i=10;i<100;i++){  
if(!(i%7)) //7的倍數
break;  
cout<<i;  
}
ans:直接印出10,11,12,13
```

***  
#### ***函式***  
* ***函式的架構***  
函式為``結構化設計``一個重要元素，可將複雜的程式分解為較小、較簡單的問題，使程式可讀性增加、偵錯及修改也較為容易  
函式結構包含了:  
i. 函式雛形(prototype)  
ii. 函式本身(敘述)  
iii. 函式引數(arguments)  

(可分為``函數宣告``、``函數定義``、``函數呼叫``三個部分，其中函數定義最為重要)  

函式宣告及定義的語法:  
```  
型態 函式名稱(型別 引數1,型別 引數2,...);  //宣告

OR

型態 函式名稱(型別 引數1,型別 引數2,...)  //定義
{
敘述程式區塊...;
} 

```
ps 1:與函式語法架構類似，但不需要敘述的部分，引數部分可省略引數名稱，只寫引數型態即可，prototype的宣告在結尾要加分號，像printf()和scanf()這類的基本函數雛形宣告，都已經包含在#include<stdio.h>標準輸出與輸入的標頭檔內，故可直接使用  
ps 2:一般放在函數定義以及函數呼叫之前  
ps 3:若沒有引數參數可用void表示或者空白不打，而函式名稱前的「型態」代表函數傳值回來(使用return敘述)的資料型態。如果函式本身不需要傳值回來，那麼就把「型態」設定為``void``  
ps 4:記得函式定義，其名稱之後一定有一對小括號()，而且之後不要加上分號;函式宣告時要加上分號  

函式呼叫語法:  
```  
型態 函式名稱(引數1,引數2,....)  
```  
ps:型態:函式傳回的資料型態，任何一個介紹過的資料型態，也可為各種型態的指標  
   函式名稱:可自訂，不可與變數名稱重複或為保留字  
   引數:欲傳遞進函式的引數  
```   
ex:
#include <stdio.h>
#include <stdlib.h>
int  max (int, int) ;               //  函數宣告
int  main (void)
{
    int  a, b;
    printf("請輸入兩個數：");
    scanf("%d %d", &a, &b);
    printf("最大數是：%d \n", max(a, b) );      //  函數呼叫
    system ("pause");
    return  0;
}

int  max(int  x, int  y)           //  函數定義
{
    if  (x >= y)      return  x;
    else              return  y;
}
```
* ***引數的傳遞***  
每個函數是獨立的，因此當需要外部的資料時，或是在函式內修改到外部資料時，就必須將資料以引數的方法傳遞函式，引數又稱做『傳入值』，傳回值型態就是f(x)答案的型態，可能是整數、小數、字元、運算式...等等。  
C語言本身就是由許多函數所構成，一開始由main()函式出發，有呼叫另一個函式，則跳入該函式，執行完之後，再回到主函式main()繼續執行。   
函式可以有傳入值，也可以有回傳值，利用return敘述可以將變數傳回呼叫它的函式內，一但執行到return敘述，程式將直接結束此函數的執行，將後方的值傳回原先呼叫的函式。  
* ***區域與全域變數***  
區域變數->每個變數都有生命週期(scope)，當一個變數被宣告時，也決定了這個變數該存在的範圍，變數宣告要在程式最上方，只存在於該程式區塊中，離開該程式區塊(大括號)，該變數就會被銷毀，故在不同區塊內的變數名稱是可重複的。
全域變數->在程式一開始即宣告，宣告於所有函式之外，其作用範圍是整個程式。  
* ***變數儲存類別***  
(1) extern修飾字:  
用於告訴編譯器，此變數已在其他地方宣告了，不在配置記憶體給該變數  
語法`` extern type var-name;``  
ps:前置處理器是在編譯器編譯程式前進行作用，#include的作用就是將相關的檔案含括進來使用  
第一種->#include <filename> 使用角括號會在系統設定的含括檔目錄中去尋找  
第二種->#include "filename" 使用雙引號會在目前檔案的工作目錄去尋找檔案，還可以指定路徑去尋找檔案，例如 #include"d:/bill.h"   
(2) register修飾字:  
register是CPU上的memory，CPU要存取register的資料遠比存取memory裡的資料要快。因此C語言提供了register修飾字，讓變數可以持續留在CPU的register內，藉此增加運算的速度，通常迴圈次數頻繁，控制迴圈次數的變數就可用register來宣告，可節省時間  
(3) static修飾字  
可以使變數只初始化一次  
 ex:  
``` 
int main(void)  
{  
int i;  
for(i=1;i<5;i++)  
printf("x=%d\n",f());  
system("pause");  
}  
int f(void)  
{  
 static int x=0;  
 return x++;  
}
```  
因為變數x使用了static修飾，只會被初始化一次，不會再下次進入時一再被指定為0                
(4) const修飾字  
被const修飾的變數不能被更改

* ***遞迴函式***  
一個函式直接或間接(在敘述內呼叫其他函式，在該函式內又呼叫了原先的函式)的呼叫函式本身，稱為recursive function  
ex:計算n階乘(n!)，可利用n!=n*(n-1)!來計算  
缺點:遞迴函式，容易做重複的計算，每一次呼叫函式都會再去佔用一些記憶體，故效率不佳  
                  
* ***main函式的引數***  
main()函式的引數，定義為外部傳給main()函式的引數，在執行列command prompt，類似win系統下的cmd或unix系統的shell，可以在程式後加上引數，當成是需要接受這些引數時，就可以用main()函式的引數來輸入  
ps:在C語言中，已經定義main()函式的第一個引數為執行程式本身  
***  
#### ***陣列 array***  
```
陣列優點為:
1. 容易製作，只需一行宣告  
2. 索引值與儲存資料有一對一關係，容易存取
```
```
陣列缺點為:  
1. 空間上的限制與浪費，宣告時已決定最大空間，沒有使用到的部分會造成記憶體空間浪費 
2. 當需要刪除或插入元素時，往往需要動到其他元素，效率不佳 
3. 無法對多個有順序的資料做良好的呈現
```
* ***一維陣列的使用***  
陣列為最基本的資料結構之一，宣告一個陣列等同於宣告``多個相同型態``的變數，在記憶體中是連續的。假設當一個具有3個元素的整數陣列被宣告時，程式會要求一個``連續的``記憶體位址  
宣告一維陣列語法:  
```  
資料型態 陣列名稱[元素個數];  ->int array[10]
```  
C語言中，陣列的第一個元素之索引值(index)為0，第二個為1，依此類推。一維陣列表示方法->array[0]、array[1]、array[2]...，而每一個陣列元素都代表4 bytes的整數變數  
ps:宣告陣列時，元素個數必須為常數，因為編譯器需要知道要配置多少記憶體來存放陣列  
ex:int array[n]->是不行的因為n為變數, int array[5]->可以為常數  
```  
自行輸出與輸入陣列元素的值
int num[5];
scanf("%d",&num[0]); //陣列輸入方式  
printf("%d",num[0]); //陣列輸出方式  
```  
ps:宣告陣列時其元素個數必須為常數，但使用時的索引值可為變數，甚至可為一個運算式  
```  
int i,a[10]  
for(i=0;i<10;i++)  
a[i]=i;  
```  
上述索引值從0開始，a[10]不是合理的使用範圍，也就是說一個具有n個元素陣列被宣告時，索引值的範圍為0~n-1  
設定陣列元素除了一個個指定之外，下列為其它陣列元素設定方式:  
```
int a[5]={0}; //陣列的值皆為0  
int b[3]={10,20,30}; //宣告時使用大括號設定初值  
int c[]={5,2,6,9,7}; //陣列元素個數依初值設定個數而定  
```  
* ***用陣列來表示字串***  
因c語言中並沒有字串型態，如需使用字串，通常會運用陣列與索引值來表示。在C語言中，以``字元'\0'``判斷一個字串是否結束了，因此如果一個字串由n個字元組成，儲存這個字串的陣列大小為n+1個字元  
ex:  
```  
char name[6];  
name[0]='j';  
name[1]='a';  
name[2]='\0';  //指定'\0'給陣列元素  
name[3]='s';
name[4]='0';  
name[5]='n';  
程式只會輸出『ja』，因為遇到了\0，被認定此字串到此結束  
```  
* ***二維和多維陣列***  
宣告二維以上陣列的語法:  
```  
型態 陣列名稱[元素個數(1維)][元素個數(2維)]...[元素個數(n維)];  -> ex: int a[5][5];
```  
元素的資料型態為整數型態，從a[0][0],a[0][1]...a[0][4]....a[4][4]。  
* ***將陣列傳遞進函式***  
陣列也可當作引數，傳遞進函式時，不會將陣列複製一份，而是將陣列第一個元素的記憶體位址傳遞進函式，所以在函式內修改陣列的值是有效的
***
#### ***指標***  
* ***指標的定義***  
指標(pointer)是C語言當中一項非常重要的資料結構，可用來製作堆疊、佇列...等資料結構，用來存放在記憶體中的位址。並擁有自己的運算子。透過指標存取變數時，因各種變數儲存方式不同，編譯器需要了解的是如何解釋這一塊記憶體，因此宣告變數時，需告知變數為``指標型態``或``指標變數``所指向的記憶體型態。而指標就是``某變數的位址``，指標變數則是用來存放指標的變數。
ps:指標變數本身均佔有4個元組(bytes)  
宣告指標的語法:  
```  
型態 *變數名稱; OR 型態* 變數名稱;   

(型態:指標指向記憶體位址所儲存變數之資料型態  
*變數名稱:表示這是一個指標型態的變數)    
```
變數三要素:變數位址、變數值、變數名稱
變數的位址，稱為「指向該變數的指標」  
``*&b->從b這個位址中取址``
指向整數型態變數的指標->整數指標  
指向浮點數變數的指標->浮點數指標  
最基本的運算子有兩個(有順序，需先取得記憶體位址才能取得記憶體位址的值):  
『 & 』->稱為取址運算子，取得變數或陣列元素的``記憶體位址``，後方運算元為一個``變數``  
『 * 』->稱為依址取址運算子，用來取得指標所指向記憶體位址中的``值（內容）``，後方運算元為一個``記憶體位址``  
ex:  
```
#include <stdio.h>
 
int main(void) {
    int b = 2;
    int* pointer = &b;
 
    printf("變數 b 的值：%d\n", b);
    printf("變數 b 的地址：%p\n", &b);
    printf("pointer 的值：%p\n", pointer);
    printf("\n"); //換行
    
    *pointer = 100;
 
    printf("*pointer 的值：%d\n", *pointer);
    printf("變數 b 的值：%d\n", b);
    printf("變數 pointer 的地址：%p\n", &pointer);
 
    return 0;
}
```  
ps:我們可以看到一開始的變數 b 的值被設定為 2，所以印出來也會是 2。然後用「&b」取出變數 b 的地址「0x7fff551b49c8」。
由於 &b 的值被賦予給 pointer，所以把 pointer 印出來後同樣也是「0x7fff551b49c8」。由於 * pointer 就是其指向的變數 b，所以在這邊我們試著把 * pointer 中的值改成 100， b值也會變成100。最後，由於存放 pointer 這個變數的地址，和變數 b 的地址不一樣，所以利用「&pointer」後，可發現地址「0x7fff551b49c0」和變數 b 的地址不一樣。  

使用指標時有幾點需要注意 ps:  
(1) 指標需指向正確的型態  
ex:  
```  
double *ptr;  
int a;  
ptr=&a;  
*ptr=5;  
```  
當指向double型態的指標時，會修改 8 bytes的記憶體。但變數a實際只佔了4個bytes，另外4 bytes可能正在被程式使用，會造成錯誤的發生。  
(2) 不可用&運算子對常數或運算式取指標值  
ex:  
```  
int *ptr;  
ptr=&3;  //不可用&運算子對常數取指標值
ptr=&(a+b); //不可用&運算子對運算式取指標值  
```  
(3) 不可在指標並未指向任何記憶體時使用``*``運算子  
ex:  
```
int * ptr;  
*ptr=1;  
---------
int count=9;  
int a;  
int *b;  
a=count;  //(O) (int)=(int)  
b=count;  //(X) (int *)=(int)  
a=&count;  //(X) (int)=(int *)  
b=&count; //(O) (int *)=(int *)  
```  

* ***指標的運算***  
不像一般變數的四則運算，對於指標只有「+」、「-」、「++」、「--」->針對各個資料型態的長度來處理位址的加減法運算  
使用``加法``的意義為：將指標``往後移動n個``該型態的記憶體  
ex:  
```
int * ptr,a;  
ptr=&a;  
ptr++;
```  
執行後，指標ptr將指向變數a記憶體位址後方的4個bytes的記憶體位址  
  
使用``減法``的意義為:將指標``往前移動n個``該型態的記憶體  
ex:  
```
int * ptr,a;  
ptr=&a;  
ptr=ptr-20;  
```
執行後，指標ptr將指向變數a記憶體位址前方的「20 * 4 bytes」的記憶體位址  

* ***指標與陣列的關係***  
指標與陣列息息相關，當一個陣列被宣告時，陣列名稱可當作指標使用，指向該型態陣列的第一個元素  
ex:  
```
int * ptr,a[10];  
ptr=a+5;  
printf("%d %d",* a,* ptr);
```  
上述範例宣告了一個指向整數型態的指標和一個具有10個整數元素的陣列，a指向陣列的第一個元素，加上5後指向第六個元素，設定給指標變數ptr，因此第三行會印出a[0]與a[5]的值。陣列名稱雖視為指標，但不可任意修改。  
ps:陣列本身名稱為一指標，指向第一個元素，不是指向整個陣列，但使用sizeof運算子想找出陣列大小時，陣列名稱又代表了整個陣列  
```  
int a [3];  
printf("%d",sizeof(a));  
```  
因為陣列具有三個int型態的元素，3 * 4等於12  

* ***將指標當引數傳遞進函式***  
在C語言中，可以利用指標解決在函數間傳遞多個回傳值的問題，可以將指數當作引數來傳入函式中，因指標紀錄了變數的記憶體位址，可以利用指標進行資料修改。
```
#include <stdio.h>
#include<stdlib.h>
void vset(int,int);
void rset(int*,int);
int main(void)
{
  int x=0,*p;       
  p = &x;            
  vset(x,1);            
  printf("x = %d ",x);
  rset(p,1);          
printf("x = %d\n",x);
system("pause");     
}
void vset(int x,int y)
{
  x = y;
}
void rset(int *p,int y)
{
  *p = y;              
}
```
vset函式修改的是區域變數x，與main()函式內的變數x不相關，所以第一個x=0。rset函式* p=y敘述修改的是p所指向的變數，也就是main()函式內的變數x，所以第二個x的值變成1  
 
* ***多重間接參照***  
指標本身也具有記憶體位址，所以宣告一個指向指標型態變數的指標是合法的。指標若是存放另一個指標變數的位址，這種指向指標的指標稱為雙重指標  
宣告格式:  
``型態 **指標變數;``  
```  
int **pp,*p,x=5;  
pp=&p;  
p=&x;  
** pp=10;  
```  
* ***函式的指標***  
 程式在執行時，除了變數在記憶體中。程式本身也在記憶體中，當一個指標指向一個函式時，可以間接使用指標呼叫該函式，而函式指標的型態必須與函式回傳型態相同  
```
#include <stdio.h>
#include<stdlib.h>
int add(int,int);
int main(void)
{
  int ans,(*p) (int x,int y); //宣告函式指標p，具有兩個整數引數
  p = add;      //將p指向函式add      
  ans = (*p) (3,4);      //間接呼叫add函式
  printf("%d\n",ans);
system("pause");    
}
int add(int x,int y)
{
  return x+y;
}
```
***  
#### ***字串***  

* ***字串與陣列***  
C語言的字串是以字元陣列的方式呈現，有些微不同，字串必定會以「\0」字元結束，而字元陣列則沒有這種限制。除了將字元一個個指定進入陣列外，還提供了較為簡易的宣告方式。
宣告字元方式:  
``char s[]="This is a string" ``  
編譯器會自動調整陣列的長度，將字串放置進陣列  

* ***字串的輸出與輸入***  
輸出字串最基本的方式  
ex:  
```  
int i;  
char s[]="This is a string" ;
for(i=0;s[i]!='\0';i++)
printf("%c",s[i]);
```  
(1)  
上述是將組成字串的字元，一個個印出。其實``printf()``函式也有支援字串的輸出格式%s，C語言另提供一個基本輸出字串函式為``puts()函式``。  
其宣告語法如下: ``int puts(const char *str) ; or  puts(字元陣列名稱);``  
puts函式接受一字元指標的引數，他會從該位址開始將字元輸出直到遇到'\0'字元後停止，接著再印出換行控制(\n)，puts()函式與printf()函式再加上換行字元意義相同。  

(2)  
接受使用者輸入字串，可以使用``scanf()函式``，scanf()函式會接受空白字元或是使用者按下enter鍵前的字串，因此若希望整行字串被儲存下來，可以使用``get()函式``  
其宣告語法如下:  
``char *gets(char *str); or gets(字元陣列名稱);``  

* ***簡介字串處理函式***  
C語言提供了多個標準的字串處理函式。ex:strcat()、strncat()、strchr()、strrchr()、strcmp()、strncmp()...等。使用時記得將string.h標頭檔涵括進來，語法如下:  
``#include <string.h>``. 

(1) strcat()與strncat()函式:連結字串
strcat()與strncat()可以將兩個字串連接在一起，函式雛型宣告如下:  
```
char * strcat(char * str1,const char * str2);  
char * strncat(char * str1,const char * str2,size_t len);  
```  
strcat()->會將str2字串連接在str1字串後，再回傳str1的記憶體位址    
strncat()->會根據引數len，決定字串str2連結幾個字元至字串str1，最多連接len個字元，若len值大於str2字串的長度，則會全部連接，作用等同於strcat()函式  

(2) strchr()與strrchr()函式:尋找字元  
用於在字串中尋找一個字元，函式雛型宣告如下:  
```
char * strchr(const char * str,int ch);  
char * strrchr(const char * str,int ch);  
```  
strchr()->會在引數ch視為char型態，在str字串中尋找第一個出現的ch，若有找到，則回傳所在的位址，若沒有找到則回傳NULL值   
strrchr()->會將引數ch視為char型態，在str字串中尋找最後出現的ch，若有找到，則回傳所在的位址，若沒有找到則回傳0值  

(3)strcmp()與strncmp()函式:比較字串  
比較兩個字串，根據結果回傳不同的值，函式雛型宣告如下:  
```
int strcmp(const char * str1,const char * str2);  
char strncmp(const char * str1,const char * str2,size_t len);  
```   
strcmp->比較兩字串str1,str2，若兩者相同則回傳0，若str1字元值(從第一個字元開始比較)小於str2則回傳負值，若str1字元值大於str2則回傳正值  
strncmp()->與strcmp()函式類似，但strncmp()函式最多只會比對len個字元，限制比對的字元數  

(4) strcpy()與strncpy函式:複製字串  
將一個字串的內容複製至另一個字串，它們的雛型宣告如下:  
```
char * strcpy(char *to,const char *from);  
char * strncpy(char *to,const char *from,size_t len);  
```  
strcpy()->會將from字串(連同'\0')複製至to字串，之後傳回to字串的位址  
strncpy()->會根據引數，從from字串最多複製len個字元至to字串  

(5) strlen()函式:計算字串長度  
會計算字串的長度，並回傳字串的長度(含空格)，函式雛型宣告如下:  
``size_t strlen(const char * str);``  
***  
#### ***前置處理器***  
程式原始碼->compile->可執行檔(.exe)。在編譯前c語言的前置處理器會對程式原始碼做一些處理，包括加入一些程式碼、取代特定字串或選擇性略過某些原始碼。也可用於製造巨集，取代一些簡單函式的功能。對於C語言模組化非常有用，當以``#``符號開頭，就為前置處理器，只單純做文字處理，其後敘述也不必使用分號結尾
* ***#include 指令***  
 最常使用的前置處理器指令之一，將某個file置入程式後在編譯，故C語言開頭會有#include<stdio.h>的敘述，就是將stdio.h標準輸出入標頭檔引入，才可使用printf()、scanf()...等基本函式  
 
 #include指令，一般使用格式有兩種:  
 (1) #include <filename>  //會先搜尋預設放置標準函式庫的目錄，再將該檔案置入程式碼當中  
 (2) #include "filename"  //會先搜尋當前工作目錄(主程式碼放置目錄)，再將該檔案置入程式碼當中，在程式開發引入自己撰寫的標頭檔時常使用  

* ***#define 指令、#undef指令與巨集的使用***  
使用前置處理器可節省使用的變數空間  
#define指令可用來定義常數或巨集，語法如下:  
``#define 識別子 字串``  
在前置處理器時，只會做字串工作，將程式裡所有的識別子，取代為後方的字串(變數)。經過#define指令所定義的識別子，並不是一個變數，所以無法更改它的值。而識別子也可有引數的存在，語法如下:  
``#include 識別子1(識別子2,識別子3...) 字串(運算式)``  ->這樣的宣告方式就可以製作``巨集``。另外，利用``#undef指令``可將之前#define過的識別子取消  
ex1:  
#define add(x+y) x+y  
printf("%d",add(2,3));  
ex2:  
#undef NUM  
#define NUM 50  

* ***#if、#else、#ifdef、#ifndef和#endif指令***  
#if 、#else和#endif指令其使用語法如下:  
```  
#if 判別式  
程式區塊;  
#endif  
```  
ps:當判別式為真值(True)時，編譯其下方的程式區塊直到#endif為止;當判別式為偽值(False)時，下方的程式區塊將不會被編譯。  

``` 
#if 判別式  
程式區塊;  
#else  
程式區塊;  
#endif  
```  
ps:當判別式為真值(True)時，編譯其下方的程式敘述直到#else為止;當判別式為偽值(False)時，#else下方直到#endif的程式敘述將會被編譯  

#ifdef與#ifndef指令其使用語法如下:  
```  
#ifdef 識別子  
程式區塊；  
#endif  
```  
ps:#ifdef->會根據識別子是否被定義，當被定義時，下方直到#endif的程式敘述將被編譯，反之則不被編譯  

```
#ifndef 識別子  
程式區塊;  
#endif  
```  
ps:#ifndef與#ifdef相反，當識別子未被定義時，下方直到#endif的敘述將被編譯，反之則不編譯  

* ***#error指令***  
#error指令通常用在程式的偵錯，語法如下:  
``#error 錯誤訊息(ex:字串,數字)``  
當編譯器遇到#error指令，將會把編譯的相關資訊(程式名稱、行數等等)以及錯誤訊息印出  

***  
#### ***結構、聯合與列舉***  

* ***結構(Structure)***  
使用好的資料型態設計程式，可以增進程式的效率和可讀性。結構是資料的集合，在結構的``資料型態``，可以包含各種型態的變數或是陣列，也可以在結構內包含另外的結構，使用彈性大，其宣告的語法如下:  
```
struct 結構名稱{  
結構成員1->資料型態 欄位名稱_變數1;  
結構成員2->資料型態 欄位名稱_變數2;  
...  
};  

OR  

二維的座標軸，有Ｘ軸和Y軸座標
struct 結構名稱{  
結構成員1->資料型態 欄位名稱;  
結構成員2->資料型態 欄位名稱;  
...  
}結構變數;  

我們也可以直接把變數宣告在結構的後面  
結構名稱 結構變數(多個變數可以以逗點隔開);  

ps:可以使用「.」運算子來存取結構成員，又稱為直接選取運算子，延續上方宣告的結構。  
其中結構變數，都將參考一樣的樣板，有著一樣的結構
```  
ex:  
struct animal{  
char name[10];  
int sex;  
}dog,cat ;  
dog.sex=1;  
cat.sex=0;  
gets(dog.name);  
gets(cat.name);  

* ***將結構傳遞進函式***  
結構也可作為函式的引數傳入函式之中  
```  
int cmp (struct animal s1,struct animal s2)
{  
return s1.sex==s2.sex;  
}  
```  
* ***結構與指標***  
結構也可以使用指標來間接存取，當``指標指向一個結構變數``，使用結構指標存取結構的成員時。需使用``「->」``間接選取運算子  
```
struct friends{  
char birth[10];  
int sex;  
char name[10];  
}f[10];  

int main(void) 
{ 
int i;  
struct friends *p =f;  //指向friends結構的指標p
for(i=0;i<10,i++,p++)
{  
scanf("%s",p->birth);  
scanf("%d",&p->sex);  
scanf("%d",p->name); 
} 
} 
ps 1:其中p是一個指標，存取結構中的字元陣列birth時，直接使用「->」，不需再加上&運算子，也就是說指向結構內的成員birth為一個指標，指向一個字元陣列，因此可直接放在scanf()函式後當引數  
ps 2:使用「->」運算子時，並不需使用「*」運算子取得結構實體，然後配合「.」運算子去取得結構內的成員  
ex:p->sex 不需要用(*p).sex方式
```
* ***聯合 (union)***  
聯合與結構的宣告方式相似，其宣告的語法:  
```
union 聯合名稱{  
聯合成員1;  
聯合成員2;  
...
}聯合名稱;
```  
聯合內的所有成員是``共用記憶體位置``，成員間不需要是相同型態，但同一時間只能以一種型態來解釋該塊記憶體  

ex:  
uniom my_union{  
int i;  
float f;
};  

int main(){  
union my_union un;  //union可加可不加  
un.i=10;  
un.f=10.25;  
printf("%d %f",un.i,un.f);  
return 0;  
}  

OR  
 
uniom my_union{  
int i;  
float f;
}un;  

int main(){  
un.i=10;  
un.f=10.25;  
printf("%d %f",un.i,un.f);  
return 0;  
}  
ps 1:透過上方例子可以發現當 un.f 被設值後， un.i 的值就不對了。事實上，那就是 10.25 的 float 型態二進位值，直接用 int 的方式去解析，所以顯示了一個像是亂數的值。也因為這種特性，當要故意讓 C 語言以錯誤的型別去讀取資料時，可以透過 union 。  

ps 2:此範例宣告了一個聯合ul，具有３個成員，變數a、字元陣列b與浮點數c，在記憶體中使用同一塊空間配置變數，而存取聯合成員與結構成員相同，同樣使用「.」與「->」運算子。而 union 的大小，就是 union 結構中型態的最大值，如果 union 中宣告了一個 short (2 bytes)，和一個 double (8 bytes)，那這個 union 的大小就會是 8 bytes。  

* ***列舉型態 (enumeration)***  
列舉可以定義一組指派給變數的具名整數常數，可將數個整數常數命名，所列舉變數可指定為其中之一個整數變數，宣告的語法如下:  
``` enum 列舉名稱 {整數常數1,整數常數2,...}變數名稱;```  
ex 1:   
enum people{female,male} mary;  

ps 1:上方的範例宣告一個列舉型態，名稱為people，具有female整數常數與male整數常數，編譯器會自動初始化整數常數，使得female為0，male為1，並宣告一個列舉變數mary，可將mary指定給其中的任何變數  

ex 2:  
mary=female;  
if(mary==female)  
printf("mary is a women");  

ps 2:列舉變數就是整數型態的變數，列舉變數也可儲存不再列舉宣告內的數值，但為了程式結構明確性不建議使用  


* ***typedef 指令***  
自訂型態(typedef) 沒有定義新型態的功能，但可以將現有的型態以新的名稱表示，節省程式撰寫的時間，也可使程式更加益讀且較有結構，宣告語法如下: 
``typedef 舊資料型態名稱 新資料型態名稱;``  
ex:  
typedef struct skill{  
int head;  
int tail;  
int body;  
} SKILL;  
SKILL snl;  
  
ps: 上方範例，SKILL並不是結構變數，而是typedef所定義的新型態名稱，最後一行使用SKILL來宣告一個結構變數snl，效果等同於使用struct skill宣告  

***
#### ***輸出入與檔案操作***   

* ***控制台(console)的I/O***  
C語言當中兩個最基本的輸出入函式:printf()和scanf()函式  
(1) printf()函式  
雛形宣告如下:  
```int printf(const char * control_string,arguments...);```  
ps:printf()函式會依據控制字串control_string的格式，輸出至螢幕上，在control_string中可使用一些特殊符號，來產生換行效果或是往後去對應argument內的變數輸出，可用的特殊符號如下:  
(變數轉換符號)%d->整數, %f->浮點數,%lf->雙精度浮點數,%c->字元,%s->字串,%%->印出%,\\->印出\,%e->浮點數(科學記號，小寫的e),%E->浮點數(科學記號，大寫的E),%g->在%e,%ｆ中較短的表示法，不列印不必要的0和小數點,%o->八進位整數(無正負號),%x->十六進位整數,%p->指標位址,\'->印出',\''->印出'',\n->換行,\b->逼一聲,\t->Tab  

ps:上述輸出格式不為%%,%c,%p時，可以指定輸出的最小寬度(使用幾格輸出)，或是小數點的位數  

ex:  
printf("%5d\n",10); ->最小寬度5，因此在印出10之前會有三格空白  
printf("%2.4f\n",12.35); ->最小寬度2，小數點寬度四格，因小數點後會以空白補齊列出12.3500  
printf("%-5d\n",20) ->其中「-」符號是指定printf函是在輸出時「向左對齊」，一般默認為向右對齊，故在輸出20後會有三個空白  
 
(2) scanf()函式  
雛形宣告如下:  
```int scanf(const char * control_string,arguments...);```  
scanf函式與printf函式類似，根據控制字串的描述，等待使用者輸入資料，使用者輸入後儲存到後方arguments的記憶體位置內，control_string區域可使用的特殊符號包含:%d->讀入整數(有正負號),%u->讀入整數(無正負號),%f->讀入浮點數,%c->讀入浮點數(科學記號,小寫的e),%o->八進位整數(無正負號),%x->十六進位整數,%p->指標位址,%s->讀入字串  
ps:scanf也可指定最小寬度，它會限制儲存進變數的位數個數，不建議使用。在儲存字串時，當遇到空格或換行字元時就會結束，因此我們常常使用gets函式來取得字串而非scanf函式  

(3)getchar()輸入函式與putchar()輸出函式  
兩函式的雛形宣告如下:  
``` 
int getchar(void);  
int putchar(int ch);
```
getchar()函式會要求使用者輸入一個字元，並回傳該字元的ASCll值，這是因為當getchar()發生錯誤時，會回傳EOF(定義在stdio.h中的負整數值)，所以會以int型態回傳，不過在使用時也可以直接以一個char型態變數來接受getchar()的回傳值，c語言會自動做型態的轉換  
putchar()函式會將引數中的ch輸出至螢幕上，與getchar相同，當函式執行成功時，putchar會以int型態回傳該字元的ASCll值，若失敗則回傳EOF  

* ***串流(Stream)的概念***  
C語言中，為了提供對系統I/O有一致性的介面，建立了一個抽象的概念，稱為串流(Stream)，也就是一連串的資料，C語言中的檔案等同於字元的串流，許多裝置都可視為串流，包含:螢幕、鍵盤、記憶體、磁帶...等等，都可以串流來達到輸出入行為上的一致性。  
可分為兩種:  
1. 文字串流 (Text stream):處理文字串流時，串流的內容為一個個ASCll字元，但對於特殊字元(\n)，會做特殊處理，轉換為應有的格式，因此寫入的串流資料並不會與寫入檔案的資料完全相同  
2. 二進位串流 (binary stream):寫入串流的資料將與寫入檔案的資料完全相同，存取這兩種串流模式的函式也不同  
C語言定義了三種基本串流:stdin、stdout與stderr  
(1) stdin(standard input):標準輸入的串流，使用者輸入的資料會放置在這  
(2) stdout(standard output):標準輸出的串流，所有輸入到螢幕上的資料會放置在這  
(3) stderr(standard error):標準錯誤輸出的串流，在這個串流內的資料會被輸出到螢幕上，不過作業系統或程式可根據輸出資料所在的串流，判斷是否要做紀錄，通常stderr會被作業系統留下記錄檔  

* ***檔案的I/O***  
C語言使用串流的概念進行檔案處理，檔案的I/O方式是:``宣告一個FILE型態的指標``，指向一個開啟的串流，藉由間接存取指標來讀取或寫入檔案。  

(1) fopen()與fclose()函式:串流的開啟與關閉，雛形宣告如下:  
```  
FILE *fopen(const char *fname,const char *mode);  
int fclose(FILE *stream)  
```  
ps 1: fopen()函式會嘗試以mode字串來記錄資料的模式，開啟以fname字串為名稱的檔案，並回傳一個串流;若開啟失敗，則回傳NULL指標。fclose()函式會嘗試關閉引數中的串流，成功則回傳0，失敗則回傳EOF(end of file)  
ps 2:fopen()函式的mode有很多種包含:"r"->開啟一個檔案，只能讀取 ,"w"->開啟一個檔案，只能寫入 ,"a"->只能以附加在最後的方式寫入檔案 ,"rb、wb、ab“->開啟一個二進位檔案，只能附加在最後 ,"r+"->開啟一個檔案，可以讀取及寫入;若檔案不存在，則回傳NULL ,"w+"->建立一個檔案，可以讀取及寫入，若檔案存在，則刪除原檔 ,"a+"->開啟一個檔案，可以讀取及寫入，若檔案不存在，則建立新檔, "rb+、wb+、ab+"->開啟一個二進位檔案，用法與上述相同  

(2) fgetc()與fputc()函式:從串流中輸出入字元  
可從串流中輸出與輸入單一個字元，它們的雛形宣告如下:  
```  
int fgetc(FILE *stream);  
int fputc(int ch,FILE *stream);
```  
fgetc函式的引數為一個串流，fgetc函式從串流中取得下一個字元，回傳該字元值，若遇到錯誤或是檔案已經結束時則回傳EOF  
fputc函式會將第一個引數轉換為char型態，將此字元寫入串流stream中，若成功則回傳該字元，失敗則回傳EOF  
ex:  
```
#include <stdio.h>
int main(void)
{
  char ch;  
  FILE *fp;  
  if((fp=fopen("12-3-1-textfile.txt","r")) == NULL) exit(1);
  while((ch = fgetc(fp)) != EOF)
    fputc(ch,stdout);  //將字元一個個輸出到stdout(螢幕)
  fclose(fp);
  system("pause");
}  
```  


(３) fgets()與fputs()函式:從串流中輸出入字串  
可以指定串流輸出入字串，它們的雛形宣告如下:  
```  
char *fgetc(char *str, int num,FILE *stream);  
int fputc(char *str, FILE *stream);
```  
ps 1:fgets函式會從stream內讀取字串，直到遇到(\n字元)，或是直到num個字元被輸入，之後存入字元陣列str中，不同於gets函式，fgets會將換行字元也儲存。若fgets函式執行成功，則回傳str，反之則會傳NULL  
ps 2:fputs函式會將字串str輸出至stream，不同於puts函式，fputs函式不會自動在輸出完畢後加上換行字元，而puts函式則自動換行。若fputs函式執行成功則回傳一個非零值，反之則回傳EOF  
ex:  
```
#include <stdio.h>
int main(void)
{
  char buf[80];
  FILE *fp;
  if((fp=fopen("12-3-1-textfile.txt","r")) == NULL) exit(1);
  while(fgets(buf,80,fp) != NULL) 
    fputs(buf,stdout);
  fclose(fp);
  system("pause");
}  
```
(4) fprintf()與fscanf()函式:串流輸出入函式   
與先前的printf和scanf函式功能相同，只是多加了一個指標引數，使其可以指定串流輸出，函式雛形宣告如下:  
```  
int fprintf(FILE *fp, char *control string, arguments...);  
int fputc(FILE *fp, char *control string, arguments...);  
```   

(5) fread()與fwrite()函式:二進位串流輸出入函式   
是專門用在二進位串流的I/O函式，好處在於對於數值的輸出入，不必轉換為字元形式，效率上會比較好，而且在二進位的串流下，不限制任何型態的I/O，只注意目前輸出或輸入了多少個位元組  
```
size_t fread(void *buffer,size_t size, size_t num, FILE *fp);  
size_t fwrite(void *buffer,size_t size, size_t num, FILE *fp);  
```
ps:void型態的指標，可以指向任意型態的指標，因此這兩函式存取型態不受限制  
ps 1:fread()函式會從二進位串流的目前位置，讀取num個大小為size的為元組，之後儲存進入buffer陣列(任意型態)，最後回傳成功讀取的資料數。藉由回傳值是否等於num值，可以判斷檔案是否讀取完畢，回傳值等於num時，表示檔案讀取已結束   
ps 2:fwrite()函式會從buffer陣列中，取num個大小為size的位元組，寫入二進位串流，最後回傳值為成功寫入的位元組，如果回傳值小於num值，則表示輸出過程發生錯誤  

(6) fseek()、ftell()與rewind()函式:變更在串流內的位置函式  
可設定檔案指標在串流中的位置，串流都是直線型的，往下走就無法回頭，這三個函式使我們不必重新開啟串流，可以直接改變目前所在位置，設置在串流內自由移動，程式雛形宣告如下:  
```  
int fseek(FILE *fp,long offset,int origin);  
long ftell(FILE *stream);  
void rewind(FILE *stream);  
```  
ps 1: fseek函式可設定檔案指標在串流中的位置，會從指定的origin位置，移動offset個位元組，若fseek函式更改成功則回傳0，更改失敗則回傳非零值  
ps 2: ftell函式會回傳stream的目前位置，若發生錯誤則回傳-1  
ps 3: rewind函式會將stream的目前位置設為該stream的開頭  

***
#### ***動態記憶體配置***    
假設現在必須紀錄不明大小的物件，並分析這些物件，首先必須將所有物件獨進記憶體中，但不到執行期間，不會知道，到底一次有多少物件被讀入，因此需要動態配置記憶體機制    
 
* ***動態配置記憶體函式介紹***  

(1) malloc()函式:呼叫動態記憶體  
malloc會向作業系統要求記憶體，它的函式雛形宣告如下:  
``void *malloc(size_t size);``  
ps:此函式會向作業系統要求一塊大小為size位元組的記憶體空間，之後回傳指向該記憶體的指標  

ex 1:  
int * p;  
p=(int *) malloc(sizeof(int));  
ps 1:使用malloc函式向作業系統要求一塊大小等同於int型態的記憶體，使用sizeof時，可以避免不同作業系統的int型態大小不的狀態，回傳時先將型態轉換為指向int的指標型態，在指定記憶體位址給p，接下來就可利用指標p間接存取這塊記憶體。而當使用者使用結構時，結構大小並不一定等同成員大小的總和，因此在使用malloc()配置記憶體時，最好不要直接指定位元組，而應使用sizeof 運算子找出需要的大小      

(2) free()函式:釋放記憶體空間  
可以釋放程式要求配置的記憶體空間，它的函式雛形宣告如下:  
``void free(void* ptr);``
ps:接收一個指向程式配置的記憶體指標，將該記憶體釋放，每當程式配置一塊記憶體時，系統會在該記憶體上做標記，防止其他程式更改該記憶體資料，free()函式可以告知系統把標記刪除，若每次配置完記憶體都不使用free函式清除，系統可使用的記憶體空間會越來越少，就容易產生當機，，而系統並不會自動將程式所配置的記憶體釋放，所以每當使用malloc()或其它動態配置記憶體時，必定要使用free函式釋放該空間  

(3) realloc()函式:可更改配置記憶體大小  
可將已配置的記憶體空間更改大小，它的雛形宣告如下:  
``void * realloc(void *ptr,size_t size);``  
ps:realloc函式接受兩個變數，指向配置過的記憶體指標以及欲更改記憶體的大小，使用realloc函式，可將配置過的記憶體變得更大或更小，若加大記憶體，原先儲存的記憶體不變，多出的記憶體空間沒有定義;若減少記憶體，則原先的資料會盡可能往新記憶體空間儲存  

(4) calloc()函式:動態配置記憶體  
與malloc函式相同，也是配置記憶體的函式，唯一不同是calloc函式，所配置出的記憶體``會自動將值設為0``，會要求一塊大小為num(元素) * size大小(型態的一個陣列)的記憶體，通常使用在陣列的記憶體呼叫中  

***
#### ***類別 (Class)***  
C++加入了物件導向的概念，而類別就是物件導向設計核心。可以使用class來定義一個物件(object)。而這個物件包含許多他的資訊。類別是物件的定義，物件是類別的實例。  
類別是一種使用者自訂的資料型態，由許多資料型態集合而成，主要包含兩個部分：  
```
(1) 資料成員(data member)：可以在類別中定義多種資料型態的變數，如int、char、float、string  
(2) 成員函式(member function)：類別中還包括存取成員的函式  
```
程式被看作是相互協作的物件集合，所有類別構成一個透過繼承關係相聯繫的層次結構  
物件導向程式設計就是先決定所要的類別，然後給每個類別提供完整的操作，最後使用繼承來表現其共同點，以模組化為核心概念，以封裝、繼承、多型...等方式為原則，產生具有可重用性、可維護性以及可擴展性的軟體  
類別和結構的差別在於class也可以包含「函式」，而class中的標籤有三種保留字標籤:
```
i. public->公開的。此屬性能夠自由地被同一類別內的方法或是物件外的程式碼，及對於類別或類別成員的進行存取或修改，完全無限制   
ii. private->私有的。此標籤下就是標記為私有，表示只有在這個class內的方法可以存取，才可以使用這些變數或函式，或使此class的``「朋友(friend)」``也可以  
iii. protected->保護的。介於兩者之間，為同類別和具有``繼承``關係的類別具有存取權限  
ps:如果沒有使用任何標籤的話，C++會自動將它歸類為private  
```
* ***基本結構***  
class與struct有些類似，宣告語法如下:  
```
class 類別名稱{  
類別標籤1:  
類別成員1;  
類別成員2;  
...  
類別標籤2:
類別成員3;
類別成員4;
...
}變數名稱;

OR

類別名稱 類別變數;
```

* ***類別的基本使用***  
要使用class就像宣告其他型態變數一樣，而當我們要使用類別內物件的內容函式時
```  
class Cuboid{
int x,y,z;
public:
void set_value(int,int,int);
int volume();
}; 

Cuboid cuboid1; 
```
以下範例成功宣告了一個名為cuboid1的Cuboid物件，當我們要使用這個物件的內容函式時，利用``「.」``來呼叫
```
cuboid1.set_value(1,2,3);
cuboid1.volume();
```
定義class內成員函式的方式有兩種:一種是直接在class內宣告該函式時定義。另一種是在class之外定義  
```
void Cuboid::set_values(int, int, int){
函式內容;}
ps:利用「::」此符號來標示函式所屬的class，來標示函式所屬的class。而使用class優點在於當我們使用到多個相同類別物件時就很明顯了

ps:public下的所有東西都可以被其他函數直接呼叫，而Private標籤中必須使用Public中有定義到的member fucction 才能讀取。可以避免資料不小心被其他函數破壞
```

* ***建構子及解構子***  
是類別中比較特別的成員函式。當我們使用一個class變數，解構子或建構子會自動(或半自動)對每個變數做起始與清除的動作  
其中``建構子(constructor)``作用就是在變數被創造時所執行的函式，若沒有定義任何建構子，系統會自動使用初始建構子，若我們定義了有傳入參數的建構子，就必須手動呼叫。``建構子的名稱與類別名稱相同，且不能有回傳值，所以連回傳型態都不用宣告``  
``解構子(destructor)``和constructor相反，當變數生命週期結束時，會自動呼叫，而解構子的名稱與類別名稱相同，只是前面多了``「~」``字元，不用回傳任何值  
```
test::test(){
x=1;
y=1;
z=1;
}  
而當我們宣告一個test變數時: test t1;

也可以定義有傳入值的建構子
three::three(int a,int b,int c){
x=a;
y=b;
z=c;
}
當我們宣告一個three變數時 test t1(2,4,5);
```

* ***重載運算子***  
在C++中，可以對int 或double等基本資料型態做運算子操作，但並不能將兩個物件相加，利用定義重載運算子(overriding operators)就可以達到利用運算子操作物件的功能  
定義:  
```
傳回值類別名稱:operator 運算子 (參數) {
函式內容；
}
```

* ***static 成員***  
類別中的函式是共用的，而參數是每個物件有自己的一份參數。static成員就是宣告class中的某一個參數是被共用的，不管創造了幾個這個類別的物件，static的參數就只會有一份  
用法如下:
```
static 參數型態 參數名稱;
```

* ***friend 函式***   
通常在類別內宣告為private的參數和函式，是不能在此物件以外的地方取的和使用，但若使用friend函式就可以打破此限制，可取得被private所保護的類別成員  

* ***friend 類別***   
與上一個friend函式十分相近，可以宣告類別1是類別2的「朋友(friend)」，則類別一就可以取用類別二的private成員

* ***繼承(Inheritance)***
繼承是C++物件導向的重要特色之一，繼承可以讓我們在撰寫程式時，不用重新定義一些相似的類別。  
```
/* 繼承 */
#include <iostream>
using namespace std;
class Rectangle{ //長方形類別
    protected:
        int x,y;
    public:
        void set_values_(int a,int b){
            x=a; y=b; }
        int area( ) {return x*y;}
};

class Cuboid: public Rectangle { //長方體類別
    private:
        int z;
    public:
        void set_values(int a,int b,int c){
            set_values_(a,b); z=c; }
        int volume( ) {return  area()*z;}
};

int main(void)
{
    Cuboid C1;
    C1.set_values(1,2,3);
    cout<<"C1 體積: "<< C1.volume( )<<endl;
    return 0;
}
```
ps:在長方體類別中，比起長方形類別只多定義了高的資訊，繼承的方式為:在一開始宣告Cuboid類別處多加了``「:public Rectangle」``，也就是宣告Cuboid公開(public)繼承長方形rectangle類別，此時長方形為父類別，長方體為子類別。而其中``public繼承``是最常用的一種繼承方式，代表子類別繼承的成員會和父類別一樣，ex:area() public繼承到長方體中還會是public，但private成員仍無法被其他類別使用，而protected標籤下的成員，可以被子類別使用  

* ***保護(protected)繼承與私用(private)繼承***  
protected和private繼承，保護繼承和公開繼承的差別，僅在於父類別的物件繼承到子類別後，都會屬於「protected」標籤。使用保護繼承的目的是希望只有子類別以及繼承子類別的類別，才能使用到父類別的成員，而私用繼承則是從所有父類別繼承到子類別，都會屬於「private」類別  

* ***繼承結構子與解構子***  
只要子類別建立物件，不管是用預設建立建構子或有傳入參數的建構子，系統都會自動呼叫父類別的預設建構子，再呼叫子類別自己的建構子，若子類別想要使用有傳入參數的父類別建構子，則可以利用「:」來達成，用法如下:  
```
子類別建構子 ():指定(父類別)建構子{
;//建構子內容
}
```
ps:至於解構子，執行的順序則是和建構子相反，先執行子類別自己的解構子，再自動執行父類別的解構子  

* ***在繼承中重新定義函式***  
繼承時如果有父類別和子類別的函式名稱相同，則會以呼叫者的函式優先  

* ***C++物件導向的應用***  
三大特徵:  
1. 封裝(Encapsulation)  
「封裝」是藉由訂定類別屬性和方法的存取權限，來保全一個物件的內容。目的乃在於處理所謂『資料隱藏』的功用，而讓使用物件的人只能透過行為或方法來操作物件，而無法直接接觸到或更改到私有的資料  
2. 繼承(Inheritation)  
「繼承」是指可以由一個類別中衍生出更多的類別，不需要重複撰寫同樣的程式碼。可以讓我們先建立一個共通的類別，然後讓新的類別繼承共通類別的特性，再進行細部項目的修改。繼承的符號為『:』冒號，被繼承者稱為基礎類別(base class)或父類別，繼承者則稱為衍生類別(drived class)或子類別  
3. 多型(Polymorphism)  
程式會藉由不同物件所屬的不同類別，來辨識同名方法可能執行不同內容，也就是按照指標所指物件的不同或是參考物件的不同，來呼叫對應物件的成員函式  

***
#### ***排序與搜尋***  
排序(Sort)與搜尋(Search)是資料處理中很重要的問題，其中「排序」->將資料整理成一個有順序的情況 ,「搜尋」->是指一群資料中，去找到我們要找的資料。  
演算法就是一組用來解決特定問題的有限指令步驟，每個步驟都必須明確，可以按照步驟依序執行，並可在有限時間內完成。  
正確演算法的必要條件如下:``輸入、輸出、明確性、有效性、有限性``  
常見的演算法表示方式有:``文字表示法``、``虛擬碼表示法``與``流程圖表示法``  
(1) 文字表示法:用人類的自然語言來描述演算法，不過自然語言的種類繁多，不同語言之間容易產生認知差異，因此會較不準確  
(2) 虛擬碼(Pseudo Code):是一種介於自然語言和程式語言之間的表示方法以文字敘述寫出演算法的表示方法，因此兼具文字說明及程式演算的過程，結合了數學是、敘述表示式以及相關語法，優點在於要轉換成電腦程式時較容易，缺點在於較缺乏一致的虛擬碼標準  
 
* ***排序(Sort)***  
電腦排序有多種演算法，包含選擇排序法、插入排序法、氣泡排序法、快速排序法...等等  

(1) 選擇排序法(Selection sort):  
假設有n個元素，檢查第一個至第ｎ個元素，將最小元素放置在第1位，接著檢查第二個至第n個元素，將最小的放置在第2位，持續使用此方法到n-1後，便可將元素排序成由小到大了  

(2) 插入排序法(Insertion sort):  
假設有ｎ個元素，第一次拿取第一個元素，因此取出的元素已經排序好了;第二次拿出第二個元素，與第一元素做比較，比第一元素小，則放置在第一元素前，依此類推(每次取第ｎ個元素，前n-1個元素已經排序好，再將第n個元素安插進去安排好的陣列)。  

(3) 氣泡排序法(Bubble sort):  
假設有n個元素，由第一個開始，第二個元素做比較，若第一個元素比第二個元素大則兩者交換;再將第二個與第三個元素做比較，若第二個元素比第三個元素大則兩者交換;依此法一直比較到最後一個元素。做完第一輪，已經將陣列中最大元素放置最後。此時將N的問題縮小到N-1的問題，對剩下的N-1元素再做上述步驟，便可找出第二大的元素置於N-1的位置，依此類推，即可完成資料由小到大排序     

(4) 快速排序法(Quick sort):  
選擇一數作為基準數，之後將陣列分為三個部分，小於基準數的數都放置在基準數的左方，大於基準數的數都放置在基準數的右方，重複此步驟，將左右方尚未排序好的資料再進行分割與排序  

* ***搜尋(Search)***  
常見的搜尋法包含:循序搜尋法、二分搜尋法...等  

(1) 循序搜尋法 (Sequential search):  
是最直觀的搜尋法，假設欲從n個元素中搜尋出值m，從第一個元素開始比對，如果取出元素等於m值，則紀錄該索引值，循序搜尋演算法就是從頭到尾一個一個來比較。會根據資料原本的排序情形而決定搜尋速度，若欲搜尋的值不在資料內或欲找的值在資料最後面，會浪費很多搜尋時間  

(2) 二分搜尋法 (Binary search):  
會比循序搜尋法更有效率，而binary search只能用於已排序好的資料，且不依序一個個比，而是直接與陣列中間元素比較。若要搜尋數值小(key<中間值)，則找左邊列的中間元素來比較;若數值較大(key>中間值)，則找右邊陣列的中間元素來比較;若相等，則代表找到了。對於資料量龐大的時候，二分搜尋法效果就會相當顯著，但前提是必須先將``資料排序``才行  

***
#### ***堆疊(stack)與佇列(queue)***   

* ***堆疊的概念***  
堆疊為一串在操作上有``順序性``的資料。將資料儲存進入一個堆疊後，再取出時會產生後進先出**LIFO(Last-In-First-Out)**，換句話說，最後進入的元素會最早被使用    
堆疊這一種資料結構會接受I/O的命令:「push」 與 「pop」  
「push」->這個命令會將元素加入堆疊  
「pop」->這個命令會將堆疊最頂端的元素取出  
ps:利用C語言模擬堆疊操作，最簡單是使用一個陣列，以及使用一個變數來記錄目前堆疊的頂端位置  

* ***堆疊的應用***  
堆疊在電腦領域中最常見的應用就是函式的呼叫，當在一個函式呼叫另一個函式時就有堆疊的情況發生，可將函式想成一個個元素  

* ***佇列的概念***  
佇列也為在操作上有順序性的資料，但所允許操作這種資料結構的方式與堆疊不同。當資料儲存進入一個佇列時，會依照先進先出FIFO (Fisrt-In-First-Out)的規則，最早進入佇列的元素會最先被取出使用  
佇列這種資料結構會接受兩種I/O命令:「enqueue」與「dequeue」  
「enqueue」->這個指令可將一個元素加入佇列的尾端  
「dequeue」->將在佇列最前端的元素取出  
ps:使用C語言模擬佇列操作，最簡單的方式也是使用一個陣列，當對佇列做enqueue和dequeue命令時，需要維護兩資訊:佇列的前端(front)及尾端(rear)，因此我們可以將陣列及紀錄前後端的變數，使用結構(structure)來包裝起來  
ex:
```
struct queue{  
int q[100];
int front;
int rear;
};
```
ps2:上方的範例中，定義了一個佇列結構，其中包含了三個成員。第一個結構成員為陣列，儲存資料用。後面兩個成員用來記錄佇列
目前的前端與尾端位置  

* ***佇列的應用***  
佇列在電腦方面的運用，可以在作業系統的運作中發現，以前作業系統只提供單工的環境(一次處理一個使用者命令)，使用者所下的命令或是作業系統自動產生的程式，稱為一個程序(process)，可將程序想像為一個佇列元素，在單人單攻的作業系統中，程序的流程為:執行程序->結束->下一個程序;而在多人多工的環境，每個使用者產生的程序，可能會有優先權的問題，其中優先權的部分常用queue來呈現，通常稱為優先佇列(priority queue)


***
#### ***鏈接串列(Linked List)***  
Linked-list是一個有序的資料集合，其中每個元素都包含下一個元素的位址。當程式需要儲存同一類型的資料時，陣列是一個簡單的方法，而串列的出現是為了解決一些陣列的缺陷，串列的觀念是根據執行時所需記憶體大小，動態配置一塊記憶體，稱之為節點(node)，節點之間包含了連結的機制，將所有node串接在一起，稱之為串列  
* 節點之間沒有實體關係，他們不是連續儲存的，需要用指標來辨別串列的第一個節點，以及其後續的節點  
* 節點是鏈結串列中重要元素，最少有兩個欄位的結構，包含資料與串列中下一個節點的位址  
* 節點的宣告:  
```
struct node{
int number; //整數
struct node *link; //指標指向下一個node的宣告
};
ps:node的產生 head=(struct node*)malloc(siezeof(struct node));
```
* 配置新節點可以使用動態配置
```
typedef struct node NODE;
NODE* head=(NODE*)malloc(sizeof(NODE));
head->next=(NODE*)malloc(sizeof(NODE));
head->next->next=NULL;
ps:第二行使用malloc函數配置一塊新的記憶體，並回傳記憶體位址指定給指標head，作為串列第一個元素，第三行與第二行類似，產生串列第二個元素，第四行則將節點下一個元素設為NULL，表示串列結尾在此節點
```
```
串列的優點:  
1. 程式執行時可動態配置記憶體，所使用的空間可以自由增減，減少記憶體的浪費  
2. 當元素需要被插入或刪除時，不影響其他空間，以增進效率，比陣列來的簡單容易，只需利用指標加以處理但動作較複雜  
3. 也以取代陣列儲存方式(堆疊與佇列)，資料元素的數目可以彈性的增減
```
```
串列的缺點:  
1. 製作不易，需使用指標完成資料結構  
2. 沒有索引值，存取較不易  
3. 存取任一元素時，可能需經過其他元素，循序存取(無法進行二元搜尋)
```  

* ***單向鏈結串列 (Singly Linked Lists)***  
為最基本的串列，每個節點包含了:儲存的資料、指向下一個節點的指標，node結構的第一個成員data，可根據所要儲存的資料類型更改資料型態。串列通常會使用一個指標指向串列開頭，若是有一個節點next指標為NULL，則可判端為串列結尾
```
struct node{
int data;
struct node *next;
};
ps:當了解如何產生新節點、刪除元素和插入元素後，陣列可儲存的資料都可以改用串列儲存，堆疊和佇列也可以改用串列方式動態呈現
```


* ***雙向鏈結串列 (Doubly Linked Lists)***  
單向串列只能儲存下一個節點位置，只能向一個方向移動，若想知道某節點的上一個節點位址，需要重頭開始讀取串列元素，會十分浪費時間  
而利用雙向串列，以空間換取時間，在節點內不只紀錄了下一個節點位址，也紀錄了上一個節點的位址  
```
ex:  
struct dnode{  
int data;
struct dnode * prev; 
strcut dnode * next;
};
```
ps:上方節點的宣告多出了prev指標變數紀錄節點的上一個節點地址， next則紀錄著此節點下一個節點位址
