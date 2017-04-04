---
title: "Umowy dotyczące projektu"
description: "Ten artykuł zawiera opisy i przykłady umów dotyczących projektów, które można tworzyć dla różnych typów projektów i źródeł finansowania, oraz opis metod zarządzania umowami i fakturowania odbiorców projektów w programie Microsoft Dynamics 365 for Operations."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectContractsListPage, ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23561
ms.assetid: bfd18d9b-d9a6-4e21-bc95-bf4af45f617f
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: 969a95ddfede4614a346ca07032f4514187de8f2
ms.lasthandoff: 03/31/2017


---

# <a name="project-contracts"></a>Umowy dotyczące projektu

Ten artykuł zawiera opisy i przykłady umów dotyczących projektów, które można tworzyć dla różnych typów projektów i źródeł finansowania, oraz opis metod zarządzania umowami i fakturowania odbiorców projektów w programie Microsoft Dynamics 365 for Operations.

Typ projektu tworzonego dla umowy dotyczącej projektu określa metodę wystawiania faktur dla klientów projektu. Umowę dotyczącą projektu i powiązany projekt można zmienić, ale nie można zmienić typu projektu. 

Za pomocą umowy dotyczącej projektu można fakturować jeden lub kilka projektów w tym samym czasie. Umowa dotycząca projektu pozwala zapewnić spójną procedurę fakturowania każdego podprojektu w strukturze projektu. 

Każdy projekt, dla którego zostanie wystawiona faktura, musi być skojarzony z umową dotyczącą projektu. Ustawienia dla umowy dotyczącej projektu są stosowane do wszystkich projektów i podprojektów, które są skojarzone z umową dotyczącą projektu. 

Umowa dotycząca projektu może określać jedno lub więcej źródeł finansowania. Dzięki temu można podzielić fakturę między wielu płatników, skonfigurować limity finansowania tak, aby źródła finansowania nie były wyświetlane na rachunku dla więcej niż określonej kwoty i skonfigurować reguły finansowania dla rozchodów związanych z opłatami.

## <a name="funding-for-project-contracts"></a>Finansowanie umów dotyczących projektów
Niektóre umowy dotyczące projektu określają, że kilka podmiotów finansuje koszty projektu. Oto kilka przykładów:

-   Duży odbiorca, który ma wiele oddziałów, prosi o podzielenie finansowania projektu między oddziały.
-   Twoja firma dzieli koszty dużego projektu z organizacją zewnętrzną.
-   Projekt drogi jest wspólnie finansowany przez dwie gminy.
-   Projekt mostu jest finansowany z dotacji rządowej oraz ze środków firmy prywatnej.

W programie Microsoft Dynamics 365 for Operations można podzielić rozliczenie jednej transakcji lub całego projektu między wielu odbiorców, grantów lub organizacji. 

W przypadku projektów, które mają wiele fundatorów, wszystkie strony partycypujące w finansowaniu zaawansowanego projektu są nazywane źródłami finansowania. Po zdefiniowaniu odbiorcy, organizacji lub dotacji jako źródła finansowania można je przypisać do jednej lub kilku reguł finansowania. Reguły finansowania zawierają kryteria, które określają sposób podziału opłat między różne źródła finansowania projektu. 

Ponieważ towarów magazynowych, takich te, które są pojawiają się w zapotrzebowaniach na zakup i zamówieniach zakupu, nie można podzielić, kwoty kosztów nie można rozdzielić między wiele źródeł finansowania na etapie dystrybucji. Dlatego wartość źródła finansowania pozostaje 0 (zero) do momentu zaksięgowania wydania zapasów. Po zaksięgowaniu wydania zapasów kwota kosztu jest rozdzielana zgodnie z regułami dystrybucji konta dla projektu.

Poniżej przedstawiono niektóre czynności, które można wykonać, aby podzielić fakturowanie między kilka źródeł finansowania:

-   Określ, że wszystkie transakcje w ramach projektu używają tej samej waluty sprzedaży co umowa dotycząca projektu.
-   ustaw limity finansowania. Dzięki temu dla jednego źródła finansowania nie zostaną wystawione faktury na kwotę wyższą niż kwota określona w projekcie.
-   Ustaw reguły finansowania i limity finansowania dla każdego pracownika, pozycji, kategorii, grupy kategorii i typu transakcji (lub dla wszystkich typów transakcji).
-   Wybierz opcjonalne daty rozpoczęcia i zakończenia, aby zdefiniować okres ważności każdej z reguł finansowania.
-   Określ wartość procentową, za którą odpowiada każde źródło finansowania.
-   Określ, które źródło finansowania jest odpowiedzialne za finansowanie różnic wynikających z obliczeń alokacji finansowania.
-   Ustaw reguły określające jak koszty projektu będą fakturowane dla odbiorców zewnętrznych i jak będą obciążały organizacje wewnętrzne.
-   Zapisz transakcje na zablokowanym koncie finansowania dopóki nie będzie możliwe uzyskanie dodatkowego finansowania lub nie zostanie podjęta decyzja o finansowaniu kosztów z wewnętrznego źródła.

Aby określić, która grupa podatku ma zostać skojarzona z transakcją, projekt zostanie przeszukany pod kątem przypisania grupy podatku. Jeśli na etapie projektu nie została przypisana grupa podatku, zostanie przeszukana umowa dotycząca projektu.

### <a name="example-multiple-funding-sources-simple"></a>Przykład: Wiele źródeł finansowania (uproszczone)

Poniższa tabela zawiera scenariusze zarządzania alokacją finansowania między wiele źródeł finansowania. Scenariusze te opierają się na następujących założeniach:

-   Ustawienia priorytetu są uwzględniane w alokacji środków przed zastosowaniem innego kryterium reguły finansowania.
-   Nie określono zakresu dat w celu zdefiniowania okresu ważności reguły.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Scenario</strong></td>
<td><strong>Źródło finansowania </strong></td>
<td><strong>Procent alokacji </strong></td>
<td><strong>Priorytet alokacji </strong></td>
</tr>
<tr class="even">
<td>Chcesz alokować koszty do jednego źródła finansowania do czasu wyczerpania się jej funduszy, alokować koszty do drugiego źródła finansowania do momentu wyczerpania jego funduszy, a na koniec pozostałe koszty przydzielić do trzeciego źródła finansowania.</td>
<td><ul>
<li>Źródło finansowania 1</li>
<li>Źródło finansowania 2</li>
<li>Źródło finansowania 3</li>
</ul></td>
<td><ul>
<li>100%</li>
<li>100%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>2</li>
<li>3</li>
</ul></td>
</tr>
<tr class="odd">
<td>Chcesz alokować 75% kosztów do jednego źródła finansowania i 25% kosztów do drugiego źródła finansowania. Gdy oba źródła finansowania zostaną wyczerpane, chcesz zapłacić pozostałą kwotę z trzeciego źródła finansowania.</td>
<td><ul>
<li>Źródło finansowania 1</li>
<li>Źródło finansowania 2</li>
<li>Źródło finansowania 3</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>2</li>
</ul></td>
</tr>
<tr class="even">
<td>Chcesz alokować 75% kosztów do jednego źródła finansowania i 25% kosztów do drugiego źródła finansowania. Gdy wszystkie te źródła finansowania zostaną wyczerpane, chcesz podzielić pozostały koszt między trzecie i czwarte źródło finansowania.</td>
<td><ul>
<li>Źródło finansowania 1</li>
<li>Źródło finansowania 2</li>
<li>Źródło finansowania 3</li>
<li>Źródło finansowania 4</li>
</ul></td>
<td><ul>
<li>75%</li>
<li>25%</li>
<li>50%</li>
<li>50%</li>
</ul></td>
<td><ul>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>2</li>
<li>2</li>
</ul></td>
</tr>
<tr class="odd">
<td>Chcesz alokować pierwsze 25% kosztów do jednego źródła finansowania, a resztę do drugiego.</td>
<td><ul>
<li>Źródło finansowania 1</li>
<li>Źródło finansowania 2</li>
</ul></td>
<td><ul>
<li>25%</li>
<li>100%</li>
</ul></td>
<td><ul>
<li>1 przypada na wpłatę z zysku na rzecz budżetu państwa</li>
<li>2</li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="example-multiple-funding-sources-complex"></a>Przykład: Wiele źródeł finansowania (złożone)

Masz trzy źródła finansowania, których chcesz użyć w następującej kolejności:

1.  Użyj równomiernie źródeł finansowania 2 i 3, aż do wyczerpania środków źródła 2.
2.  Kontynuuj korzystanie ze źródła finansowania 3 aż do jego wyczerpania.
3.  Użyj 1 źródła finansowania 1 po wyczerpaniu środków źródła 3.

Aby zrealizować ten cel, musisz wykonać następujące czynności:

-   Ustaw limity finansowania dla źródeł 2 i 3 jako odpowiednie kwoty.
-   Utwórz następujące reguły finansowania:
    -   Reguła 1 (Priorytet 1): Alokacja 50% transakcji do źródła finansowania 2 i 50% do źródła finansowania 3.
    -   Reguła 2 (Priorytet 2): Przydziel 100% transakcji do źródła finansowania 3.
    -   Reguła 3 (Priorytet 3): Przydziel 100% transakcji do źródła finansowania 1.

Ta konfiguracja zostanie wykonana, ponieważ transakcje są sprawdzane pod kątem reguł i limitów i system sprawdza, czy któreś z nich ma zastosowanie do transakcji. Jeśli transakcji nie dotyczą żadne reguły ani limity, zostanie zastosowana reguła Wszystkie transakcje. Reguła Wszystkie transakcje pasuje do wszystkich transakcji. 

Jeśli zostanie znaleziona reguła pasująca do transakcji, najpierw zostanie zastosowana wartość procentowa ustalona dla tej reguły, ale tylko po sprawdzeniu dopasowań pod kątem ustalonych limitów. Jeśli limit został osiągnięty, a źródło finansowania jest wyczerpane, reguła finansowania powiązana z limitem finansowania zostanie pominięta; program sprawdzi czy jest kolejna reguła do zastosowania. 

W niektórych przypadkach do reguły można przydzielić tylko część transakcji. Może się tak zdarzyć, gdy limit zostanie osiągnięty podczas alokacji transakcji. W takim przypadku tylko ograniczona kwota zostanie alokowana zgodnie z regułą, np. po 50% do każdego źródła finansowania. Dotyczy to przypadku reguły 1 opisanej wcześniej. Reszta jest rozdzielana zgodnie z następną regułą w sekwencji. 

Poniższa tabela przedstawia ten scenariusz w bardziej szczegółowy sposób.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>Zespół </strong></td>
<td><strong>Details</strong></td>
</tr>
<tr class="even">
<td>Reguły finansowania</td>
<td><ul>
<li>Reguła 1 (Priorytet 1): Wszystkie transakcje. Alokacja do źródła finansowania 2 na poziomie 50% i źródła finansowania 3 na poziomie 50%.</li>
<li>Reguła 2 (Priorytet 2): Wszystkie transakcje. Alokacja do źródła finansowania 3 na poziomie 100%.</li>
<li>Reguła 3 (Priorytet 2): Wszystkie transakcje. Alokacja do źródła finansowania 1 na poziomie 100%.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Limity finansowania</td>
<td><ul>
<li>Limit źródła finansowania 1 = 10 000,00</li>
<li>Limit źródła finansowania 2 = 500,00</li>
<li>Limit źródła finansowania 3 = 750,00</li>
</ul></td>
</tr>
<tr class="even">
<td>Transakcja 1</td>
<td><strong>Kwota transakcji:</strong> 100,00<strong>Finansowanie:</strong> transakcja jest opłacana zgodnie z regułą 1, ponieważ transakcja opłacana jest w pełni po zastosowaniu reguły 1. Transakcja jest finansowana równomiernie ze źródeł finansowania 2 i 3.
<ul>
<li>Źródło finansowania 2: 50,00</li>
<li>Źródło finansowania 3: 50,00</li>
</ul></td>
</tr>
<tr class="odd">
<td>Transakcja 2</td>
<td><strong>Kwota transakcji:</strong> 5,000.00<strong>finansowanie:</strong> transakcja opłacana jest według wszystkie trzy reguły. <strong>Reguła 1</strong><ph id="t1">
</ph><ul>
<li>Źródło finansowania 2: 450,00</li>
<li>Źródło finansowania 3: 450,00</li>
</ul><bpt id="t2">
< silne ></bpt> Zasada nr 2</strong><ph id="t3">
</ph><ul>
<li>Źródło finansowania 3: 250,00 (= 750,00 – 50,00 – 450,00)</li>
</ul><bpt id="t4">
< silne ></bpt> Reguła 3</strong><ph id="t5">
</ph><ul>
<li>Źródło finansowania 1: 3850,00 (= 5000,00 – 450,00 – 450,00 – 250,00)</li>
</ul></td>
</tr>
<tr class="even">
<td>Łączne kwoty rozdzielone na wszystkie źródła finansowania</td>
<td><ul>
<li>Źródło finansowania 1: 3850,00</li>
<li>Źródło finansowania 2: 500,00</li>
<li>Źródło finansowania 3: 750,00</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="billing-rules"></a>Reguły fakturowania
Podczas negocjowania umową dotyczącej projektu z odbiorcą, można zdefiniować, jak i kiedy można wystawiać faktury dla odbiorcy z tytułu pracy w zakresie projektu. Po skonfigurowaniu umowy dotyczącej projektu oraz projektu, można skonfigurować reguły fakturowania dla projektu. Reguły fakturowania opierają się na warunkach projektu, które są określone w umowie dotyczącej projektu. Reguły fakturowania, które można utworzyć zależą od warunków umowy dotyczącej projektu i typu projektu, np. Czas i materiały lub Stała cena, który można skojarzyć z regułą fakturowania. Można utworzyć tylko jedną regułę fakturowania dla kontraktu projektu. Regułę fakturowania można przypisać do wielu projektów, które są skojarzone z umową dotyczącą projektu i posiadają podobne warunki fakturowania. 

Można skonfigurować następujące typy reguł fakturowania:

-   **Jednostka dostawy**— Wystawianie faktury dla odbiorcy po zakończeniu jednostki dostawy. Istnieje możliwość zdefiniowania jednostek dostawy w umowie.
-   **Postęp**— Wystawianie faktury dla odbiorcy po ukończeniu określonego procentu projektu. Można skonfigurować regułę fakturowania, która automatycznie obliczy procent pracy wykonanej lub ręcznie obliczy procent pracy wykonanej, a także kwotę, na którą należy wystawić fakturę dla odbiorcy.
-   **Punkt kontrolny** — wystawianie faktury dla odbiorcy na całą kwotę w punkcie kontrolnym po jego osiągnięciu.
-   **Opłata**— Wystawianie faktury dla odbiorcy za usługi plus opłatę od zarządzania, zazwyczaj stanowiącą procent od kosztów usług.
-   **Czas i materiały**— Wystawianie faktury dla odbiorcy dla wartości z tytułu czasu i materiałów wykorzystanych w projekcie.

Dla wszystkich typów reguł fakturowania można określić procent zatrzymania do odliczenia od faktur dla odbiorcy, dopóki projekt nie osiągnie uzgodnionego etapu. Procent zatrzymania płatności został określony w umowie dotyczącej projektu. Kwota jest obliczana na podstawie i odejmowany od całkowitej wartości wierszy w fakturze dla odbiorcy. 

Dla reguł fakturowania **czas i materiały** i **postęp** użycia reguł fakturowania, można przypisać kategorie płatne. Kategorie płatnych wskazują transakcje, które należy uwzględnić na fakturach dla odbiorcy. 

Gdy jesteś gotowy do wystawienia faktury dla odbiorcy projektu, kwota do zafakturowania dla projektu jest obliczana na podstawie reguł fakturowania, a następnie generowana jest faktura projektu. 

Poniższe sekcje zawierają przykłady, które ilustrują sposób ustawiania i zarządzania regułą fakturowania dla projektu.

### <a name="example-create-a-billing-rule-that-is-based-on-the-number-of-units-delivered"></a>Przykład: Tworzenie reguły fakturowania na podstawie liczby jednostek dostawy

Twoja organizacja podpisuje umowę na przeprowadzenie cyklu pięciu szkoleń dla pracowników odbiorcy. Cena jednego szkolenia wynosi 10 000. Faktura odbiorcy jest wystawiana po zakończeniu każdego szkolenia. 

Konfigurując reguły fakturowania dla umowy, używasz następujących wartości:

-   Jednostka dostawy to jedna sesja szkolenia.
-   Cena jednostkowa to 10 000 dla sesji szkoleniowej.
-   Łączna liczba jednostek to pięć sesji szkoleniowych.

Po zakończeniu jednej sesji szkoleniowej, można utworzyć fakturę na 10 000 z tytułu pierwszej dostarczonej jednostki dostawy i wysłać fakturę do odbiorcy.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-manual-calculation"></a>Przykład: Tworzenie reguły fakturowania na podstawie określonego procentu ukończenia projektu (obliczanie ręczne)

Organizacja będąca firmą konsultingową specjalizująca się w oprogramowaniu, zawiera umowę z odbiorcą, dotyczącą opracowywania części produktu, który jest opracowywany przez odbiorcę. Organizacja zgadza się dostarczać kod oprogramowania przez okres sześciu miesięcy. Odbiorca zgadza się na zapłacenie organizacji całkowitej kwoty równej 100 000 z tytułu wykonanej pracy. Tworzysz regułę fakturowania przy rozliczaniu odbiorcy na podstawie procentu pracy wykonanej nad projektem, jak określono w umowie.

-   Na koniec pierwszego miesiąca należy spotkać się z odbiorcą w celu określenia procentu pracy wykonanej. Po sprawdzeniu projektu okazuje się, projekt został zrealizowany w 15%.
-   Tworzysz fakturę na 15 000 (15% ze 100 000) i wysyłasz do odbiorcy.

### <a name="example-create-a-billing-rule-that-is-based-on-a-specified-percentage-of-project-completion-automatic-calculation"></a>Przykład: Tworzysz regułę fakturowania na podstawie określonego procentu ukończenia projektu (obliczanie automatyczne)

Twoja firma zajmująca się tworzeniem oprogramowania, wyraża zgodę na opracowanie pakietu księgowania listy płac dla odbiorcy za kwotę 30 000. Odbiorca zgadza się na zapłacenie wynagrodzenia organizacji obliczonego na podstawie procentu zakończonej pracy. Oszacowane koszty projektu wynoszą 20 000. Umowa dotycząca projektu określa kategorie pracy, których można użyć w procesie fakturowania. Należy zdefiniować reguły fakturowania, które obliczą automatycznie kwoty faktury dla procentu wykonanej pracy dla poszczególnych kategorii. Skonfiguruj budżet dla każdej kategorii:

-   **Programowanie** — Koszt w wysokości 15 000 i dochody wysokości 20 000
-   **Instalacja** — Koszt w wysokości 5000 i dochody wysokości 10 000

Podczas tworzenia faktury dla odbiorcy po raz pierwszy, kwota faktury jest automatycznie obliczana na podstawie następujących informacji:

-   Po miesiącu pracy, pracownik zatrudniony przy projekcie przesyła kartę czasu pracy dla projektu. Koszt godzin pracy pracownika wynosi 5000 dla programowania i 1000 dla instalacji. Praca w zakresie programowania została zakończona w 33% (koszt rzeczywisty wysokości 5000/koszt budżetowy wysokości 15 000), a praca w zakresie instalacji została w 20% (koszt rzeczywisty wysokości 1000/koszt budżetowych wysokości 5000).
-   Kwota faktury wynosi 8667 i jest automatycznie obliczana (33% z 20 000, powiększone o 20 procent z 10 000).
-   Tworzysz fakturę na 8667 i wysyłasz do odbiorcy.

### <a name="example-create-a-billing-rule-that-is-based-on-agreed-upon-milestones"></a>Przykład: Tworzenie reguły fakturowania, opartej na uzgodnionych punktach kontrolnych

Organizacja będąca firmą konsultingowa specjalizującą się w zarządzaniu, zgadza się na przeprowadzenie badania rynku dla produktu konsumpcyjnego, którego planuje sprzedać odbiorca. Odbiorca zgadza się na korzystanie z usług przez trzy miesiące, począwszy od marca, i wyraża zgodę na wypłacenie organizacji kwoty równej 50000. Projekt zawiera trzy punkty kontrolne:

-   Punkt kontrolny 1: Zbierz dane o konsumencie - 31 marca
-   Punkt kontrolny 2: Analizowanie danych konsumentów - kwiecień 30
-   Punkt kontrolny 3: Przedstawienie propozycji żywotności produktu - maj 31

Odbiorca akceptuje płatność na rzecz organizacji w wysokości 10 000 dla pierwszego punktu kontrolnego , a 20 000 do drugiego i trzeciego punktu kontrolnego. 

Podczas konfigurowania umowy dotyczącej projektu, zgadzasz się na wystawianie faktur dla odbiorcy na podstawie wypełnionych punktów kontrolnych projektu. Konfiguracja reguły fakturowania obejmuje następujące kroki:

-   Określ punkty kontrolne projektu.
-   Zdefiniuj kwotę do zafakturowania dla faktury dla odbiorcy, po zakończeniu każdego punktu kontrolnego.

Po zakończeniu pierwszego punktu kontrolnego w dniu 31 marca, zaznacz punkt kontrolny jako ukończony, a następnie utwórz fakturę na kwotę 10 000 i wyślij ją do odbiorcy. Nie można utworzyć fakturę dla punktu kontrolnego, dopóki nie zostanie on zaznaczony jako ukończony.

### <a name="example-create-a-billing-rule-that-is-based-on-services-plus-a-management-fee"></a>Przykład: Tworzenie reguły fakturowania na podstawie usługi plus opłaty od zarządzania

Twoja organizacja z branży consultingowej zgadza się na przeprowadzenie badania rynku w celu oceny rentowności produktu opracowywanego przez klienta z branży detalicznej. Warunki umowy określają, że zapewnisz usługi trzech najlepszych konsultantów ds. zarządzania w celu przeprowadzenia badania kosztu dla czasu i materiałów. Odbiorca zgadza się zapłacić 100 na godzinę plus 10-procentową opłatę za zarządzanie z tytułu godzin konsultacji, które zostały zafakturowane dla projektu. 

Podczas konfigurowania umowy dotyczącej projektu, należy utworzyć regułę fakturowania w celu dodania opłaty za zarządzanie o wysokości 10 procent opłat pobieranych z tytułu godzin konsultingowe spędzonych na projekcie. 

Po utworzeniu faktury dla odbiorcy, wystawiany jest rachunek odbiorcy dotyczący 10-procentowej opłaty od zarządzania plus koszt godzin konsultingowych. Na przykład, jeśli trzech konsultantów pracowało łącznie 200 godzin w ramach projektu, zostanie utworzona faktura na kwotę 22 000 na podstawie następującego obliczenia:

-   200 godzin przy 100 na godzinę = 20 000
-   Opłata od zarządzania wysokości 10 procent = 2000
-   Łączna kwota faktury = 22,000

Jeśli opłaty są należne dla odbiorcy, a użytkownik wybrał grupę podatków w umowie dotyczącej projektu, grupa podatku jest automatyczne wprowadzana do reguły fakturowania opłat.

### <a name="example-create-a-billing-rule-for-the-value-of-time-and-materials"></a>Przykład: Tworzenie reguły fakturowania dla wartości modułu czas i materiały

Organizacja z branży consultingowej zgadza się na zapewnienie pięciu konsultantów technicznych do pracy nad projektem oprogramowania rozwoju dla odbiorcy na następnych sześć miesięcy. Klient akceptuje płatność 150 za każdą godzinę konsultacji plus koszty materiałów biurowych. Organizacja wysyła faktury dla odbiorcy na koniec każdego miesiąca. 

Podczas konfigurowania umowy dotyczącej projektu, zgadzasz się wystawianie comiesięcznych faktur dla odbiorcy na podstawie zużytego czasu i materiałów dla projektu. Utwórz regułę fakturowania, która zawiera następujące informacje:

-   Okres umowy wynosi sześć miesięcy.
-   Skonsultowane godziny konsultingowe posiadają wartość 150 na godzinę.
-   Materiały biurowe są fakturowane według kosztów, a łączny koszt projektu nie może przekroczyć 10 000.
-   Tworzysz fakturę dla odbiorcy na koniec każdego miesiąca kalendarzowego, w trakcie trwania projektu.

Podczas pierwszego miesiąca, łącznie rejestrowanych jest 800 godzin pracy przez konsultantów pracujących nad projektem. Koszt materiałów biurowych do obciążenia projektu wynosi 2000. Dlatego na koniec miesiąca, można utworzyć fakturę na sumę 122,000, obliczoną jako 800 godzin przy 150 za godzinę plus 2000 więcej za materiały biurowe.


