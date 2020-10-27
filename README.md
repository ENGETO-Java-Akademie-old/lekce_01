<p align="center">
  <img src="https://engeto.cz/wp-content/uploads/2019/01/engeto-square.png" width="200" height="200">
</p>

# Java - 1. lekce

## Co bychom měli mít hotové

Před první hodinou byste měli mít naistalované základní nástoje, které budeme na tomto kurzu používat. Návod, jak na to, je [zde](https://github.com/xthobi/eng_java_priprava/blob/main/README.md) a v případě, že narazíte při instalaci na nějaký problém, tak nám klidně napište na Slacku a rádi Vám s tím poradíme.

## Co nás čeká

 - [Představení kurzu](#představení-kurzu)
 
 - [Představení lektorů](#představení-lektorů) a studentů
 
 - [Co je to Java](#co-je-to-java)
 
 - [Proměnná](#proměnná)
 
 - [Operátor](#operátor)
 
 - [Výraz](#výraz)
 
 - [Datový typ](#datový-typ)
 
 - [Vývojářské nástoje](#vývojářské-nástroje): [JDK](#jdk), [IntelliJ IDEA](#intellij-idea), [GIT](#git)
 
## Představení kurzu
 
Vítáme Tě v kurzu jazyka Java, který by Ti měl umožnit posunout se ve své programátorské kariéře z úplného začátečníka na úroveň někoho, kdo by si mohl troufnout na pozici juniorního programátora. Nebude to ale zadarmo - určitě totiž nebude stačit si odsedět samotnou lekci, ale budeš si muset opakovat a procvičovat probranou látku a pracovat na projektech.

Během šestnácti tříhodinových lekcí si postupně od úplných základů projdeme tvorbu programů v Javě, kde si vše zároveň ukážeme i na příkladech, seznámíme se nástroji, které se při vývoji aplikací bežně používají, projdeme si spolu celý vývojový cyklus aplikace, ukážeme si, jak se testuje a všechny tyto nově nabité znalosti nakonec dostanete šanci uvést do praxe, když si na společném projektu vyzkoušíte, jak by to vypadalo, když byste se stali programátory.
 
 ## Představení lektorů
 
 Na tomto kurzu se vám budou věnovat dva lektoři, kteří se na lekcích budou střídat, ale na Slacku nás najdete oba.
 
 ### Marek Nedbal
 
 <p align="left">
  <img src="https://github.com/ENGETO-Java-Akademie/lekce_01/blob/main/engeto_profile.jpg" width="300" height="400">
</p>
 
  - živím se jako software engineer a krom krátkého extempore na začátku mé programátorské kariéry programuji již šestým rokem právě v Javě - momentálně pro společnost, o které v rámci Java kurzu ještě nekolikrát uslyšíte - <b>Oracle</b>
  
  - učení je mým koníčkem, který jsem objevil před rokem a máloco mě potěší tak, jako radost studenta, když ho drobnými radami doštouchám k tomu, aby si na řešení problému, na kterém se zasekl, přišel skoro sám
 
 ### Lukáš Horák
 
 ## Co je to Java
 
 První vydání jazyka se datuje do roku 1995, vývoj však započal na začátku devadesátých let. Jazyk Java byl navržen jako řešení pro vývoj platformně nezávislých programů. Program napsaný v Javě tedy jde spustit na libovolném z podporovaných operačních systémů (na Windows, v Linuxu, MacOS,...). Proto má Java na rozdíl od ostatních jazyků rozdílný způsob překladu a spouštění. Většina jazyků se překládá přímo do sekvence instrukcí dané procesorové platformy, které zapíšeme do souboru (například soubor .exe ve Windows) a následně se tento soubor spouští. Java místo toho vytváří takzvaný bajtkód. To je sekvence instrukcí fiktivního procesoru. Tyto instrukce pak nelze spustit přímo přímo v procesoru počítače — spouští se ve virtuálním stroji, který se nazývá JVM (Java Virtual Machine). Výhodou tohoto přístupu je jeho nezávislost na platformě. Kdekoliv máš k dispozici JVM, můžeš spouštět jakýkoli program v Javě. Zároveň je to omezení — bez JVM program nespustíš.

Java je objektově orientovaný jazyk. To znamená, že Java není čistě objektový jazyk (vše je objekt), ale nacházejí se zde i primitivní datové typy, jež nejsou reprezentovány jako objekty. Java se proti mnoha jiným jazykům vyznačuje zejména bezpečností při správě paměti. Vývojář je plně odstíněn od práce s ní. Při práci s objekty využívá pouze reference (odkazy), ale veškerou alokaci a uvolňování paměti řeší JVM, popřípadě Garbage Collector. (V tomto rysu je Java podobná jazyku C#.)

### A jak to vypadá

```java
// popis umístění - složka
package eng.nasprvniprogram;

class CoalMine {
  
  // deklarace proměnné WHAT_IS_IN_THE_MINE, do které zároveň přiřadíme hodnotu Some quality coal
  private static final String WHAT_IS_IN_THE_MINE = "Some quality coal";
  
  /*
   * metoda main je vstupní branou do Javovského programu, kterou musí obsahovat každý program
   * a ze které voláme všechny ostatní funkce
   */
  public static void main(String[] args) {
    // cyklus, který se provádí, dokud je splněna uvedená podmínka "i < 4"
    for (int i = 1; i < 4; i++) {
      // volání naší metody mine
      mine();
    }
  }
  
  /*
   * toto je naše úžasná metoda mine, která do dolů
   * pošle jednoho trpaslíka, aby přinesl to, co najde
   */
  private static void mine() {
    // System.out.println vypíše parametr, který mu předáme, do konzole
    System.out.println("We have mined: " + WHAT_IS_IN_THE_MINE + ".");
  }
}
```
 
## Proměnná

Proměnná představuje pojmenované místo v paměti, do kterého můžeme ukládat hodnoty a na které se můžeme dále v programu odkazovat právě pomocí jeho jména.

Každá proměnná má přesně daný datový typ, který specifikujeme při její deklaraci.

Při deklaraci proměnných také můžeme použít některá kláčová slova:

- <b>static</b> - tohle klíčové slovo říká, že proměnná má existovat po celou dobu běhu programu

- <b>final</b> - tohle klíčové slovo říká, že půjde o konstantu - hodnota této proměnné nepůjde měnit

- <b>public</b>, <b>protected</b>, <b>private</b> - tato klíčová slova definují viditelnost proměnné

```java
// jména konstant píšeme vždy velkými písmeny a k oddělování jednotlivých částí používáme podtržítko _
final String ZAKLADNI_OSLOVENI = "Dobrý den,";
// jména ostatních proměnných píšeme tzv. camel case - první slovo ve jméně je celé malými písmeny
//  a každé další slovo začíná velkým písmenem, které zároveň slouží jako vizuální oddělovač
private int myAgeIsNotThisNumber = 23; 
```

Při odkazování se na proměnou již žádná klíčová slova nepoužíváme - jen její jméno.

## Operátor

Kdyby v Javě šlo vytvářet jen vytvářet proměnné, tak bysme toho moc nenaprogramovali, a proto si představíme <b>operátor</b>. Operátory umožňují provádět operace mezi jednotlivými proměnnými, od základních, jako jsou sčítání a násobení, které jistě znáte z metematiky, přes logické operátory, které jste už možná také potkali, až po bitové operátory, které možná ani během své programátrské kariéry nepoužijete.

### Typy operátorů

#### Aritmetické (zachovávají datový typ)

- <b>+</b> - operátor sčítání (a spojování řetězců)

- <b>-</b> - operátor odčítání

- <b>*</b> - operátor násobení

- <b>/</b> - operátor dělení

- <b>%</b> - operátor zbytku po dělení

#### Relační (vrací boolean)

- <b>==</b> - je rovno

- <b>!=</b> - není rovno

- <b>></b> - větší než

- <b>>=</b> - větší nebo rovno

- <b><</b> - menší než

- <b><=</b> - menší nebo rovno
  
- <b>instanceof</b> - zjištění, jestli je objekt instancí zadaného typu
  
  ```java
  Integer age = 49;
  age instanceof Integer; // true
  age instanceof String; // false
  ```

#### Logické (vrací boolean)

- <b>&&</b> - logické AND - výraz a && b je pravda tehdy, když jsou a i b pravda, jinak je nepravda

- <b>||</b> - logické OR - výraz a || b je pravda tehdy, když aspoň jeden z parametrů a a b pravda, jinak je nepravda

#### Přiřazení

- <b>=</b> - operátor přiřazení - přiřazuje hodnotu pravého operandu operandu levému

```java
int dayOfYear = 294; // zde například přiřazujeme hodnotu 294 do proměnné dayOfYear
```

#### Unární (mají pouze jeden operand a zachovávají datový typ)

- <b>+</b> - indikace kladné hodnoty

- <b>-</b> - indikace záporné hodnoty

- <b>++</b> - inkrementace operandu o jedna po vyhodnocení výrazu

- <b>--</b> - dekrementace operandu o jedna po vyhodnocení výrazu

- <b>!</b> - negace hodnoty

#### Konverze

- <b>(jmeno_datoveho_typu)</b> - tento operátor zmení datový typ operandu

#### Bitové (tyto se běžně nepoužívají)

- <b>&</b> - bitový součin

- <b>^</b> - bitová nonekvivalence

- <b>|</b> - bitový součet

- <b>~</b> - bitová negace

- <b><<</b> - bitový posun vlevo

- <b>>></b> - bitový posun vpravo

### Priority operátorů

Tak jako v matematice máme dáno, že výraz vyhodnocujeme zleva doprava a že násobení má přednost před sčítáním, tak i v Javě bylo potřeba nastavit, který operátor bude mít přednost před kterým, aby se výraz vyhodnotil vždy stejně, a aby programátoři sami věděli, jak to, co píší, bude fungovat, protože by asi nikdo z vás nechtěl, aby se výraz pro výpočet vašeho platu <b>hodinovaMzda * pocetOdpracovanychHodin - poplatekZaStravenky</b> vyhonotil tak, že by se nejdřív od odpracovaných hodin odečte poplatek za stravenky a výsledek se pak vynásobí hodinovou mzdou a vy pak budete nakonec ještě vašemu zaměstanavateli platit za to, že u něj můžete pracovat.

#### Pořadí vyhodnocování je takového:

1.) postfixové

2.) unární (unární je i operátor konverze)

3.) multiplikativní

4.) aditivní

5.) posunu

6.) relační

7.) rovnosti

8.) bitové AND

9.) bitové exkluzivní OR

10.) bitové inkluzivní OR

11.) logické AND

12.) logické OR

13.) ternární

14.) přiřazení

## Výraz vs příkaz

<b>Výraz</b> je struktura složená z oprátorů, operandů a závorek a představuje výpočet nějaké hodnoty - po vyhodnocení výrazu vždy získáme jednu hodnotu.

```java
(37 + 24) * 3 >= 124
```

Výraz může obsahovat:

- proměnné

- konstanty

- volání funkcí

- operátory

- závorky

Jeho vyhodnocování probíhá podle priorit, které jsme si popsali [zde](#pořadí-vyhodnocování-je-takového) a stejně jako v matematice jde ovlivnit pomocí závorek.

<b>Příkaz</b> popisuje nějakou konkrétní akci - v lidských jazycích by mu odpovídala věta. Narozdíl od lidských jazyků ale příkaz ukončujeme středníkem. 

```java
String cat; // příkaz říkající "vytvoř proměnnou cat datového typu String"
cat = "Felix"; // příkaz říkající "přiřaď hodnotu Felix do proměnné cat"
```
Některé výrazy se mohou stát i příkazem, při ukončení středníkem, neboť popisují nějakou akci - např. přiřazení, nebo inkrementace.

```java
int number = 12;
number++;
```

## Datový typ

Java je silně typovaný programovací jazyk, což znemaná, že každá proměnná má pevně určený datový typ a v každé promenné může vždy být uložena pouze hodnota odpovídající danému datovému typu.

Datové typy se dělí na <b>primitivní</b> a <b>neprimitivní</b> neboli referenční, protože odkazují na nějaký objekt. Primitivní datové typy jsou "základem" - popisují pouze datový typ a velikost (která se liší) a vždy mají hodnotu, kdeždo referenční datové typy mohou představovat i mnohem složitější struktury, mohou být prázdné a mnohdy nabízí i pomocné metody.

Pro jejich rozlišení existuje jednoduché pravidlo - primitivní datové typy začínají vždy malým písmenem a referenční zase velkým.

### Primitivní datové typy

- <b>byte</b> - může pojmout celé číslo z rozsahu od -128 do 127

- <b>short</b> - může pojmout celé číslo z rozsahu od -32768 do 32767

- <b>int</b> - může pojmout celé číslo z rozsahu od -2147483648 do 2147483647

- <b>long</b> - může pojmout celé číslo z rozsahu od -9223372036854775808 do 9223372036854775807

- <b>float</b> - může pojmout reálné číslo z rozsahu od -3.40282e+38 do -3.40282e+38

- <b>double</b> - může pojmout reálné číslo z rozsahu od -1.79769e+308 do -3.79769e+308

- <b>boolean</b> - může pojmout jednu logickou hodnotu - pravda nebo nepravda

- <b>char</b> - může pojmout jeden libovolný znak (UNICODE)

### Referenční datové typy

Referenčních je na rozdíl od těch primitivních teoreticky neomezený počet, a proto si zmíníme jen pár z nich:

- <b>String</b> - může pojmout libovolný řetězec
```java
String aPoem = "Roses are red, Java is hard, if I want bread, I better start.. learning!";
```
- <b>Array</b> - může pojmout libovolný počet prvků stejného datového typu
```java
String[] names = {"Martin", "Marcin", "Rasmus", "Luka", "Mihael"};
```

## Vývojářské nástroje
 
V dnešní době být programátorem neznamená dělat všechno sám a psát kód v poznámkovém bloku v potemnělé mistnosti pouze ve společnosti pizzy a plechovek od energy drinků, ale tím, jak programování proniká do všech myslitelných odvětví lidské činnosti, tak stoupá i snaha o všemožné usnadňování a unifikaci vývoje a tím vznikají "nové a lepší" programovací jazyky, vývojové sady, vývojová prostředí, balíčky znovupoužitelného kódu řešícího nějaký běžný problém, či (verzovací) systémy usnadňující společnou práci většiho počtu programátorů na jednom projektu. Některé z těchno nástrojů budeme používat i my a o těch, které budeme používat, si něco povíme níže. Hodí se také zmínit šedou eminenci vývojářských nástrojů jsou různá komunitní fóra - nejznámější z nich je [Stack Overflow](https://stackoverflow.com/) zde lze najít odpovědi na snad každý programátorský problém, jen je nutné dodržovat několik pravidel.
 
 - vždycky nejdřív hledejte a až když nenajdete stejný dotaz / problém jako ten Váš, tak se ptejte
 
 - když dostanete odpověď, co nějakou odpověď najdete, tak ji jen slepě nekopírujte - nestává se sice, že by se tam vyskytovaly odpovědi, které po spuštění přehrají Váš počítač a způsobí povstání strojů, ale je běžné, že funkční řešení, které někdo poskytl v nejlepší víře, nemůsí být tím, co potřebujete a co bude fungovat i tak, jak čekáte a proto se snažte vždy před použitím cizího kódu nalezeného na nějakém fóru mu nejprve porozumnět a až pak ho použít, připadně ho brát pouze jako nasměrování k Vašemu vlastnímu řešení
 
### JDK
 
JDK, neboli Java Development Kit je soubor základních nástrojů pro vývoj aplikací v Javě od společnosti Oracle. Obsahuje kupříkladu překladač zdrojového kódu, debugger pro ladění programu, či nástroj pro tvorbu dokumentace. Dále také obsahuje JRE - Java Runtime Environment. JRE je soubor základních tříd a podpůrných souborů určený ke spouštění Java aplikací a pakliže jste hráli třeba Minecraft, nebo editovali nějaký dokument v OpenOffice, tak jste se již s JRE, byť nevědomky, setkali. JRE také obsahuje JVM - Java Virtual Machine je takzvaný interpeter - program, který náš program řádek pořádku provádí.
Tedy:

 - <b>JDK</b> (+ JRE a JVM) pro vývoj Java aplikací
 
 - <b>JRE</b> (+ JVM) pokud chceme pouze spouštět Java aplikace

 
### IntelliJ IDEA
 
Za tajemnou zkratkou IDE (Integrated Development Enviroment) se skrývá software, který má programátorovi usnadnit samotné psaní kódu. V krátkosti by se dalo říct, že jde jen o chytrý poznámkový blok, ale většina vývojových prostředí nabízí mnohem víc. Například:

- <b>editor</b> - textový editor speciálně navržený pro editování zdrojového kódu, zvládá zvýrazňovat syntax, formátovat kód, tak aby vyhovoval nastaveným konvencím a byl pro člověka, který kód edituje, čitelnější (v některé programovacích jazycích jde všechen kód napsat na jeden řádek a vše bude fungovat, ale pokud pak přijde potřeba změnit nějakou drobnost v kódu, tak se v jednořádkovém kódu nikdo nevyzná), umí našeptávat, zvýrazňovat chyby, či automaticky uzavírat závorky

- <b>debugger</b> - je nástroj, který programátorovi umožnuje zkoumat, proč jeho program (ne)funguje tak, jak jak funguje - do "podezřelých" částí kódu si totiž může přidávat "breakpointy" - body, ve kterých se provádění programu zastaví do doby, než je sám ručně pustí, případně nabízí možnost jít po jednotlivých příkazech a v každém bodě, ve kterém se zastaví, vypíše vždy svůj oktuální stav - hodnoty proměnných a to, jak do té části kódu, ve které se nachází, došel

- <b>kompilátor</b> - je nástroj, který překládá zdrojový kód zapsaný ve vyšším programovacím jazyce (který napíšeme my v editoru) do jazyka nižsího tak, aby mu rozumněl počítač - aby vznikl spustitelný program 

- <b>integrovaný verzovací systém</b> - některá IDE mají integrovaný i verzovací systém - o tom, co to verzovací systém je, si řekneme dále - u [GITu](#GIT) verzovacího systému, který budeme používat my

- <b>object browser</b> - prohlížeč komponent nacházejících se balíčcích softwaru, jejich hierarchii, metody a proměnné

- <b>nástroje pro tvorbu uživatelského rozhraní</b> - některá IDE obsahují i nástroje pro snadnou tvorbu uživatelského rozhraní

Většina vývojových prostředí bývá navržených přímo pro vývoj v konkrétním programovacím jazyce, ale najdou se výjimky, které podporují větší počet programovacích jazyků - jednou z těchto výjimek je třeba právě IDEA, kterou budeme používat my. Její nejznámější alternativy (pokud jde o vývoj v Javě) jsou [Eclipse](https://www.eclipse.org/eclipseide/) a [NetBeans](https://netbeans.apache.org/)

#### Klávesové zkratky a další vychytávky pro vývoj IDEI

- <i>Ctrl+C</i> a <i>Ctrl+V</i> - začneme zlehka - tuhle kombinaci si jistě pamatujete ještě za základní školy, když jste tvořili "referáty". Tady se chová skoro stejně. <b>Skoro.</b> Jak už jsme si řekli, tak editor zdrojového kódu je chytřejší poznámkový blok a v tomto případě je potřeba si na todát pozor, protože pokud kopírujete kód z tohoto editoru a zase ho do tohoto editoru vkládáte, tak se Vám nezkopírují jen označené řádky, ale i kontext. Dále je také potřeba dát si pozor na kopírování větších částí kódu, když jste "včera psali něco podobného", protože z vlastní zkušenosti vím, že čím delší kód, který se někdo chystá zrecyklovat, tím větší pravděpodobnost, že tam nějakou drobnost zapomene upravit a následně mu to bude fungovat úplně jinak, než by čekal. Mnohdy je proto užitečnější použít "kód ze včera" jen jako inspiraci a nový kód napsat od nuly. (existuje i lepší způsob, jak řešit opakující se podobný kód, ale k tomu se dostaneme až v pozdějších lekcích)

- <i>Ctrl+F</i> - další z těch známejších, která i tomto editoru dělá to stejné - touto zkratkou si vyvoláte utilitu fulltextového vyhledávání v aktálně otevřeném souboru

- <i>Ctrl+Shift+F</i> - opět jde o fulltextové vyhledávání, ale tentokrát v celém projektu, který máte otevřený, případně v jeho vyrané části

- <i>Esc</i> - přepnutí se do editoru

- dvakrát <i>Shift</i> - globální vyhledávání čehokoli

- <i>Alt+Enter</i> - zobrazí Vám návrhy toho, jak by šla opravit chyba, kterou Vám editor zvýraznil

- <i>Ctrl+Space</i> - zobrazí vám nabídku s doplněním aktuálně rozepsané části kódu

- <i>Ctrl+Alt+L</i> - naformátuje kód podle nastavených konvencí

- <i>Alt+F7</i> - vyhledá Vám, kde všude je Vámi vybraný element použit

- <i>Ctrl</i> a kliknutí myší na vybraný element Vás přesune o úroveň výš

### GIT

Kdyby každou aplikaci vyvíjel a spravoval vždy jen jeden programátor, tak by třeba nebylo potřeba git, ani jiného verzovacího systému, ale tím, jak roste komplexita vyvíjených projektů a s tím i počet lidí, kteří na nich pracují (a kteří ještě migrují mazi pozicemi, odděleními a zaměstanavateli) přišla potřeba jednak spravovat již vyvinutý kód a za druhé umožnit pracovat vícero lidem na stejném projektu (a společně vyvíjet několik nových featur).

#### Základní příkazy, bez kterých se při práci s gitem neobejdeme

- <i>git config --global user.name "Marek Nedbal"</i> - nastaví vaše uživatelské jméno

- <i>git config --global user.email "kingofjava@koshmail.il"</i> - nastaví váš email

- <i>git clone https://github.com/dev-academy-challenges/minesweeper.git</i> - naklanuje projekt k vám do počítače tak, abyste s ním mohli pracovat (za adresu klonovaného repozitáže jde ještě přidat jméno oddělené mezerou, pokud ho chcete mít v jinak pojmenované složce, než jak se ten projekt jmenuje)

- <i>git branch jmeno_nove_vetve</i> - vytvoří novou větev z větve, na které momentálně jste

- <i>git checkout -b jmeno_nove_vetve</i> - vytvoří novou větev z větve, na které momentálně jste a přepne se na ni (pokud se chete jen přenpout, protože už větev máte vytvořenou, tak jen vynecháte <i>-b</i>)

- <i>git add .</i> - připraví všechny změny, které jste provedli na dané větvi, k zapsaní (za změnu se považuje vytvožení nového souboru a úprava či smazání existujícího souboru)

- <i>git commit -m "Vyvoj nove superfeatury - kostra projektu"</i> - zapíše všechny změny, které jste připravili k zapsaní a ze zmenám přidá zadanou zprávu

- <i>git push origin jmeno_vetve</i> - nahraje zapsané změny do vzdáleného repozitáře

- <i>git pull origin jmeno_vetve</i> - získá změny ze vzdáleného repozitáře, které nemáte u sebe (váš kolega tam nahrál svoji část projektu)
