---
title: Omówienie systemu Intrastat
description: Ten temat zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE).
author: EvgenyPopovMBS
ms.date: 01/13/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: kfend
ms.custom:
- "28581"
- intro-internal
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 97c2b4068f3b8d38281e637ec80f04b19d19be61
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986041"
---
# <a name="intrastat-overview"></a>Omówienie systemu Intrastat

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE). W tym temacie omówiono również proces raportowania oraz opisano wymagane ustawienia i wymagania wstępne.

Intrastat to system gromadzenia i generowania danych statystycznych na temat handlu towarami między krajami/regionami Unii Europejskiej (UE). Raport Intrastat jest wymagany w przypadku każdego produktu przekraczającego granicę innego kraju/regionu UE. W niektórych krajach/regionach obowiązek tworzenia raportów Intrastat dotyczy również usług. Na potrzeby raportów Intrastat mogą być gromadzone obowiązkowe i opcjonalne elementy. Wymagane są następujące elementy: identyfikator VAT podmiotu odpowiedzialnego za dostarczenie informacji, okres referencyjny, przepływ (przyjęcie lub wysyłka), ośmiocyfrowy kod towaru, kraj członkowski (kraj wysyłki i kraj docelowy), wartość towaru, ilość towaru (waga netto i jednostka dodatkowa) oraz charakter transakcji. Kraje/regiony mogą również gromadzić opcjonalne informacje w różnych warunkach. Do informacji opcjonalnych należą: kraj/region pochodzenia towaru, warunki dostawy, środek transportu, bardziej szczegółowy kod towaru niż 8-cyfrowy, kraj pochodzenia dla wysyłki i kraj pochodzenia dla odbioru, procedura statystyczna, wartość statystyczna, opis towaru oraz port/lotnisko załadunku/rozładunku.

## <a name="overview-of-the-intrastat-reporting-process"></a>Omówienie procedury raportowania Intrastat
W poniższych sekcjach opisano cały przebieg informacji używanych na potrzeby raportowania Intrastat.

### <a name="enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>Podanie transakcji przekraczającej granicę innego kraju/regionu UE

Faktura dla odbiorcy, faktura niezależna, faktura zakupu, faktura projektu, dokument dostawy dla odbiorcy, dokument przyjęcia produktów od dostawcy lub zamówienie przeniesienia są przenoszone do arkusza Intrastat tyko wtedy, gdy kraj/region wysyłki lub dostawy znajduje się w **UE**. Ta funkcja została rozszerzona w Microsoft Dynamics 365 for Operations (wydanie 1611) i teraz pozwala określać adresy załadunku dla transakcji wewnątrzwspólnotowych. Jeżeli adres załadunku różni się od adresu służbowego dostawcy (lub adres służbowego odbiorcy w zamówieniu zwrotu), funkcja raportowania Intrastat użyje tych informacji. Podczas tworzenia zamówienia sprzedaży, faktury niezależnej, zamówienia zakupu, faktury od dostawcy, faktury projektu lub zamówienia przeniesienia, niektóre pola, które są powiązane z handlem zagranicznym, mają wartości domyślne w nagłówku dokumentu lub w wierszu. Domyślny kod transakcji jest pobierany z odpowiedniego pola na stronie **Parametry handlu zagranicznego**. Domyślny kod towaru, kraj/region pochodzenia i województwo pochodzenia są pobierane z pozycji. Można zmienić domyślne wartości i wprowadzić inne dane związane z handlem zagranicznym, takie jak procedura statystyczna, środek transportu i port.

### <a name="use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>Używanie arkusza Intrastat do generowania i raportowania informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)

Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej. Można przenieść transakcje z faktury niezależnej, faktury dla odbiorcy, dokumentu dostawy, faktury od dostawcy, dokumentu dostawy dostawcy, faktury projektu lub zamówienia przeniesienia na podstawie kryteriów transferu ustawionych na stronie **Parametry handlu zagranicznego**. Można również ręcznie wprowadzić transakcje. W razie potrzeby można ręcznie zaktualizować przeniesione transakcje w arkuszu Intrastat. W określonych warunkach, które są ustawione na stronie **Kompresja Intrastat**, można kompresować transakcje w arkuszu Intrastat. W niektórych krajach/regionach można stosować niewielki próg wartości transakcji. Następnie transakcje poniżej tego progu można zgłaszać pod określonym kodem towaru. Kod towaru można zaktualizować w odpowiednich wierszach arkusza Intrastat, na podstawie ustawienia **dolnego limitu** na stronie **Parametry handlu zagranicznego**. Można także skompresować te transakcje na podstawie ustawienia **kompresji Intrastat**. Można sprawdzić poprawność transakcji w arkuszu Intrastat na podstawie ustawienia **Sprawdzenie ustawień** na stronie **Parametry handlu zagranicznego**. Można sprawdzić kompletność informacji w następujących polach: kraj/region, województwo, waga, kod towaru, kod transakcji, dodatkowe jednostki, port, pochodzenie, warunki dostawy, metody transportu i numer identyfikacji podatkowej. Transakcje niekompletne zostaną oznaczone jako nieprawidłowe.

### <a name="use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>Używanie arkusza Intrastat do zgłaszanie informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)

Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej. Na podstawie ustawienia **Mapowanie formatu raportów** na stronie **Parametry handlu zagranicznego** można wydrukować raport Intrastat. Można również wygenerować plik elektroniczny na podstawie ustawienia **Mapowanie formatu plików** na stronie **Parametry handlu zagranicznego**. Aby dowiedzieć się więcej o raportowaniu Intrastat, w tym o warunkach wstępnych, obejrzyj nagrania zadań dotyczące raportowania Intrastat:

  - Generowanie unijnej deklaracji Intrastat
  - Przesyłanie transakcji do systemu Intrastat
  - Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej

## <a name="prerequisites"></a>Wymagania wstępne
W następującej tabeli są podane wymagania wstępne dla raportowania Intrastat.

|  Wymaganie wstępne  |  Opis  |
|-------------------------|-------------------------|
| Ustawienia adresu | Konfigurowanie kodu ISO (International Organization for Standardization) dla krajów/regionów. |
| Firma | Konfigurowanie numerów identyfikacji podatkowej do celów importu/eksportu, wewnętrznego numeru oddziału dla importu/eksportu i kodu Intrastat przypisanego do firmy. |
| Hierarchia kategorii produktów (hierarchia sprzedaży, hierarchia zaopatrzenia) | Przypisz kody asortymentu Intrastat do węzła kategorii na karcie **Kody asortymentu** na stronie **Hierarchia kategorii**. Po przypisaniu kodu asortymentu do węzła nadrzędnego kategorii, ten kod jest stosowany do wszystkich podrzędnych węzłów kategorii. Wybrane kody asortymentu będą dostępne w widoku **Wybrane** po wybraniu kodu asortymentu w szczegółach produktu i na zamówieniu sprzedaży, zamówienia zakupu oraz w wierszach zamówienia przeniesienia. |
| Szczegóły zwolnionego produktu | Konfigurowanie następujących danych handlu zagranicznego dla zwolnionych produktów:<ul><li>**Kod asortymentu** — pozwala wybrać dowolną listę wybranych towarów pobraną z przypisanej kategorii produktów lub pełną listę kodów asortymentu Intrastat.</li><li>**Statystyczny procent sumy**</li><li>**Kraj/region pochodzenia** — umożliwia wybór domyślnego kraju/regionu, w którym towary zostały w całości pozyskane lub wyprodukowane.</li><li>**Województwo pochodzenia/docelowe** — pozwala wybrać domyślne województwo docelowe dla przyjęć i województwo pochodzenia dla wysyłki.</li><li>**Waga netto w kg**</li><li>**Wyłącz** - Włącz ten parametr, aby nie przenosić transakcji z tym produktem do Intrastatu</li></ul> |
| Odbiorcy | Konfigurowanie adresu dostawy w kraju/regionie UE dla odbiorcy. |
| Dostawcy | Konfigurowanie adresu dostawcy w kraju/regionie UE. |
| Opłaty dodatkowe | Konfigurowanie kodu opłat dodatkowych w celu uwzględnienia kwoty faktury, kwoty statystycznej lub obu. Na stronie **Kody opłat** na karcie **Handel zagraniczny** włącz **wartość faktury Intrastat**, aby uwzględnić kwotę opłat w wartości faktury i włączyć **Wartość statystyczna Intrastat** w celu objęcia wartości statystycznej kwoty opłat dodatkowych.</br>Aby uzyskać więcej informacji, zapoznaj się z [przykładami kodów transakcji i opłat dodatkowych](#transaction-codes-and-miscellaneous-charges). |
| Raportowanie elektroniczne | Ustawienie konfiguracji raportu elektronicznego do eksportowania danych Intrastat do pliku w formacie żądanym przez odpowiednie organy i podglądu danych Intrastat w formacie przyjaznym dla użytkownika, który daje się odczytać (np. plik programu Microsoft Excel). |
| Magazynowanie | Skojarz konta dostawców z kodami magazynu w celu uzupełnienia numeru identyfikacji podatkowej przy przesyłaniu zamówienia przeniesienia.</br>Aby uzyskać więcej informacji, zapoznaj [się z przykładem zamówienia przeniesienia](#transfer-order).|

## <a name="setup"></a>Konfiguracja
W poniższych sekcjach opisano ustawienia, które są wymagane na potrzeby raportowania Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Ustaw wszystkie wymagane listy związane z deklaracją Intrastat

|   Lista   |   Informacje dodatkowe   |
|-------------------------|-------------------------|
| Kody asortymentu | Skonfiguruj hierarchię kategorii typu **kod asortymentu** i wprowadź wszystkie kody asortymentu zgodnie z listą. Dla każdego towaru należy zdefiniować następujące informacje:<ul><li>Nazwa i kod towaru</li><li>Przyjazna nazwa lub przetłumaczona nazwa</li><li>Ustawienia raportowania dodatkowych (uzupełniających) jednostek na karcie **Handel zagraniczny**. Można wybrać dodatkowe jednostki z listy. Można również określić, czy oprócz wybranej jednostki dodatkowej należy podać wagę towarów.</li></ul>Aby uzyskać więcej informacji, zapoznaj się z przykładem [Dodatkowe jednostki](#additional-units).|
| Kody transakcji | Ustaw charakter transakcji zgodnie z wymaganiami danego kraju/regionu. Dla każdego ustawionego kodu transakcji należy skonfigurować reguły obliczania kwot faktur i kwot statystycznych dla zamówień sprzedaży/zakupu i zamówień przeniesienia.<ul><li>Dla zamówień przeniesienia należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:<ul><li>**Puste** – kwota będzie równa 0 (zero).</li><li>**Wartość finansowa** – kwota będzie równa kosztowi finansowemu.</li><li>**Łączny koszt** – kwota będzie równa łącznemu kosztowi transakcji.</li><li>**Ręcznie** – kwota będzie równa kwocie ręcznie określonej w wierszu zamówienia przeniesienia.</li></ul></li><li>Dla zamówień sprzedaży i zakupu należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:<ul><li>**Puste** – kwota będzie równa 0 (zero).</li><li>**Kwota faktury** – kwota będzie równa kwocie fakturowana dla towaru.</li><li>**Kwota podstawy** – kwota będzie równa kwocie, która zostałaby zafakturowana przed zastosowaniem rabatów.</li></ul></ul>Aby uzyskać więcej informacji, zapoznaj się z [przykładami kodów transakcji i opłat dodatkowych](#transaction-codes-and-miscellaneous-charges). |
| Metody transportu | Ustaw tryb transportu zgodnie z wymaganiami danego kraju/regionu. Dla każdej metody dostawy można skonfigurować domyślną metodę transportu na karcie **Handel zagraniczny**. |
| Porty | Skonfiguruj port/lotnisko załadunku/rozładunku, jeśli te informacje są gromadzone w danym kraju/regionie. |
| Procedury statystyczne | Ustaw procedury statystyczne, jeśli te informacje są gromadzone w danym kraju/regionie. |



### <a name="set-up-rules-for-compressing-intrastat-transactions"></a>Konfigurowanie reguł kompresowania transakcji Intrastat

Na stronie **Kompresja Intrastat** można wybrać pola, które mają być używane dla kompresji. Wszystkie transakcje zawierające tą samą kombinację wartości dla wybranych pól w dzienniku Intrastat zostaną skompresowane w jedną transakcję podczas wykonywania funkcji kompresowania w dzienniku Intrastat.

### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

Użyj strony **Parametry handlu zagranicznego**, aby skonfigurować parametry w poniższej tabeli.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabulator</th>
<th>Parametry</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ogólne</td>
<td><ul>
<li><strong>Ogólne</strong> — pozwala określić następujące informacje:
<ul>
<li>Domyślne kody transakcji dla zamówień sprzedaży, zamówień zakupu, faktur korygujących i zamówień przeniesienia. Kod transakcji ustawiony dla faktur korygujących jest również używany jako kod zwrotu towarów fizycznych i jest używany do obsługi odchyleń zwrotów towarów fizycznych względem faktur korygujących. Zwroty towarów fizycznych są raportowane w transferze Intrastat w innym kierunku. Zwrot przesyłki jest raportowany jako nadanie, a zwrot przesyłki jako nadejście.</li>
<li>Pracownik odpowiedzialny za przygotowywanie raportów Intrastat.</li>
</ul></li>
<li><strong>Minimalny limit</strong> — pozwala określić ustawienia aktualizacji transakcji, które są poniżej progu:
<ul>
<li>Kwota i waga progu</li>
<li>Kod asortymentu do zastosowania do transakcji będących pod progiem</li>
</ul></li>
<li><strong>Przenieś</strong> — pozwala określić kryteria przenoszenia transakcji do dziennika Intrastat. Można określić, że transakcje są przenoszone tylko wtedy, gdy towary spełniają co najmniej następujące kryteria:
<ul>
<li>Towary nie są usługą.</li>
<li>Towary mają kod asortymentu.</li>
<li>Towary mają wagę.</li>
<li>Towary mają dodatkowe jednostki.</li>
</ul></li>
<li><strong>Sprawdź ustawienia</strong> — pozwala określić reguły sprawdzania kompletności danych Intrastat. Można wybrać, które dane mają być sprawdzane.</li>
<li><strong>Reguły zaokrąglania</strong> — pozwala określić następujące ustawienia do zaokrąglania kwot i wagi w raportach Intrastat:
<ul>
<li>Typ reguły zaokrąglania (precyzyjna)</li>
<li>Reguła zaokrąglania: w górę, w dół lub normalnie.</li>
<li>Liczba miejsc dziesiętnych dla kwot i wag</li>
<li>Instrukcje dotyczące zaokrąglania wag poniżej 1 kilograma (kg): w górę do 1 kg, normalnie lub bez zaokrąglania</li>
</ul></li>
<li><strong>Raportowanie elektroniczne</strong> — umożliwia określenie odwołania do konfiguracji raportowania elektronicznego, tak aby można było wygenerować plik elektroniczny i raport.</li>
<li><strong>Hierarchia kodów asortymentu</strong> — pozwala określić hierarchię kategorii typu <strong>Kod asortymentu</strong>, która reprezentuje kod asortymentu Intrastat CN8.</li>
  <li> <strong>Typ kursu wymiany</strong> — Opcjonalnie określ kurs wymiany, który ma być używany do raportowania Intrastat transakcji sprzedaży i zakupu w walutach obcych. Używane, jeśli stawka jest inna niż zastosowana przy księgowaniu transakcji.</li>  
</ul></td>
</tr>
<tr class="even">
<td>Dane kontaktowe agenta</td>
<td>Wpisywanie imienia i nazwiska, adresu numeru identyfikacji podatkowej, numeru telefonu i numeru faksu agenta.</td>
</tr>
<tr class="odd">
<td>Właściwości kraju/regionu</td>
<td>Ustawianie kraju/regionu aktualnie zaznaczonej firmy jako <strong>Krajowa</strong>. Ustawianie kraju/regionu w UE, dla kraju/regionu UE który uczestniczy w handlu wewnątrz UE z aktualną firmą, jako <strong>UE</strong>. Dla każdego kraju/regionu możesz też określić kod kraju/regionu dla handlu zagranicznego.</td>
</tr>
<tr class="even">
<td>Sekwencja numerów</td>
<td>Określanie kodu identyfikacyjnego dla dziennika Intrastat.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Przykład

### <a name="transaction-codes-and-miscellaneous-charges"></a><a name= "transaction-codes-and-miscellaneous-charges"></a>Kody transakcji i opłaty dodatkowe

W tym temacie ojmuje się scenariusz, w którym firma w Niemczech musi kupować towary od firmy we Włoszech. Aby dokonać tego zakupu, niemiecka firma musi skonfigurować nowe kody transakcji i skonfigurować reguły obliczania dla kwoty faktury i kwoty statystycznej dla tych kodów transakcji. Ponadto, gdy firma tworzy fakturę, musi określić opłaty dodatkowe i ich wartości procentowe. Te wartości będą rozważane podczas obliczania wartości statystycznej.

W scenariuszu użyto firmy **DEMF**.

#### <a name="preliminary-setup"></a>Konfiguracja wstępna

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacja** > **Firmy** i wybierz firmę **DEMF**.
2. Na skróconej karcie **Adres**, zweryfikuj czy w polu **Kraj/region** jest wartość **DEU(Niemcy)**.
3. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawy**.
4. W siatce zaznacz element **DE-001**.
5. Na skróconej karcie **Adres** wybierz pozycję **Edytuj**.
6. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **ITA**.
7. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

#### <a name="set-up-transaction-codes"></a>Ustawianie kodów transakcji

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
2. W siatce zaznacz element **11**. Następnie w okienku akcji wybierz opcję **Usuń**.
3. W okienku akcji wybierz opcję **Nowy**.
4. Na skróconej karcie **Kody transakcji** w polu **Kod** **transakcji** wprowadź wartość **11**.
5. W polu **Nazwa** wpisz **Bezpośredni zakup/sprzedaż**.
6. W sekcji **Sprzedaż i zakupy** w polu **Kwota faktury** wybierz pozycję **Kwota faktury**.
7. W polu **Kwota statystyczna** wybierz opcję **Kwota faktury**.
8. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="set-up-miscellaneous-charges"></a>Konfigurowanie opłat dodatkowych

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Ustawienia opłat** > **Kod opłat**.
2. W siatce zaznacz element **Transport**.
3. W okienku akcji wybierz pozycję **Edytuj**.
4. Na skróconej karcie **Handel zagraniczny** ustaw wartości **faktury Intrastat** i opcje wartości **statystycznej Intrastat** na wartość **Tak**.

#### <a name="set-up-foreign-trade-parameters"></a>Konfigurowanie parametrów handlu zagranicznego

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
2. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **11**.
3. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.

#### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** wybierz pozycję **DE-001**.
4. Kliknij przycisk **OK**.
5. Na karcie **Nagłówek** na skróconej karcie **Handel** **zagraniczny** sprawdź, czy w polu **Kod transakcji** znajduje się wartość **11**.
6. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia zakupu** w polu **Numer pozycji** wybierz wartość **D0003**. W polu **Ilość** wpisz wartość **10**.
7. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** w sekcji **Handel zagraniczny** sprawdź, czy pole **Kod transakcji** jest ustawione automatycznie.
8. Na skróconej karcie **Wiersze zamówienia zakupu**, w menu **Finanse**, w sekcji **Opłaty** wybierz pozycję **Obsługa opłat**.
9. W polu **Kod opłat** wybierz **TRANSPORT**.
10. W polu **Wartość opłat** wpisz wartość **30**.
11. Na okienku akcji wybierz opcję **Zapisz**. Następnie zamknij stronę.
12. W okienku akcji na karcie **Zakup** w grupie **Akcje** wybierz opcję **Potwierdź**.
13. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
14. W okienku akcji wybierz **Domyślne z**. W polu **Domyślna ilość dla wierszy** zaznacz wartość **Ilość zamówiona**. Następnie wybierz opcję **OK**.
15. Na skróconej karcie **Nagłówek faktury od dostawcy**, w sekcji **Identyfikacja faktury**, w polu **Numer** wprowadź wartość **00100**.
16. W sekcji **Daty faktury**, w polu **Data faktury** wprowadź datę **24-11-2021** (24 listopada 2021).
17. W okienku akcji naciśnij przycisk **Zaksięguj**, aby zaksięgować fakturę

### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Przeniesienie faktury od dostawcy do arkusza Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura od dostawcy** na wartość **Tak**.
4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat.

   ![Wiersz reprezentujący zamówienie zakupu z różnymi opłatami na stronie Intrastat](media/intrastat_overview_1.png)

5. Przejrzyj kartę **Ogólne** zamówienia zakupu. Zwróć uwagę, że pole **Wartość faktury** zawiera sumę pól **Kwota faktury** i **Kwota opłat za fakturę**, a pole **Wartość statystyczna** zawiera sumę pól **Kwoty statystycznej** i **Kwoty opłat statystycznych**.

   ![Szczegóły zamówienia zakupu z różnymi opłatami na karcie Ogólne na stronie Intrastat](media/intrastat_overview_2.png)

### <a name="transfer-order"></a>Zamówienie przeniesienia

W tym przykładzie firma z Niemiec musi przenieść dwie jednostki towarów z magazynu w Niemczech do magazynu we Włoszech. Dla tego produktu do księgowania w polu **Wartość statystyczna** należy również określić opłaty o stawce 20 procent. W przykładzie użyto firmy **DEMF**.

#### <a name="preliminary-setup"></a>Konfiguracja wstępna

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacja** > **Firmy** i wybierz firmę **DEMF**.
2. Na skróconej karcie **Adres**, zweryfikuj czy w polu **Kraj/region** jest wartość **DEU(Niemcy)**.
3. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
4. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.
5. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawy**.
6. W siatce zaznacz element **DE-001**.
7. Na skróconej karcie **Adres** wybierz pozycję **Edytuj**.
8. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **ITA**.
9. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

#### <a name="set-up-transaction-codes"></a>Ustawianie kodów transakcji

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Kody transakcji**.
2. W siatce zaznacz element **11**. Następnie w okienku akcji wybierz opcję **Usuń**.
3. W okienku akcji wybierz opcję **Nowy**.
4. Na skróconej karcie **Kody transakcji** w polu **Kod** **transakcji** wprowadź wartość **11**.
5. W polu **Nazwa** wpisz **Bezpośredni zakup/sprzedaż**.
6. W sekcji **Zamówienie przeniesienia** w polu **Kwota faktury** wybierz opcję **Łączny koszt**.
7. W polu **Kwota statystyczna** wybierz opcję **Koszt całkowity**.
8. Na okienku akcji wybierz opcję **Zapisz**.
9. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
10. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Zamówienie przeniesienia** wybierz wartość **11**.

#### <a name="set-up-charges-for-an-item"></a>Konfigurowanie opłat dla pozycji

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. W siatce zaznacz element **D0001**.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Opłat dodatkowych** wpisz **20**.

#### <a name="change-the-site-address"></a>Zmienianie adresu lokalizacji

1. Wybierz kolejno opcje **Zarządzanie magazynem** > **Ustawienia** > **Magazyn** > **Lokalizacje**.
2. W siatce zaznacz element **1**.
3. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
4. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **DEU**.
5. Kliknij przycisk **OK**.
6. W siatce zaznacz element **2**.
7. Na skróconej karcie **Adresy** wybierz pozycję **Edytuj**.
8. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **ITA**.
9. Kliknij przycisk **OK**.
10. Wybierz kolejno opcje **Zarządzanie magazynem** > **Ustawienia** > **Magazyn** > **Magazyny**.
11. W siatce zaznacz element **21**.
12. Na **skróconej karcie Ogólne** w sekcji **Odwołanie** w polu **Konto dostawcy** wybierz pozycję **DE-001**.

#### <a name="create-a-transfer-order"></a>Tworzenie zamówienia przeniesienia

1. Wybierz kolejno opcje **Zarządzanie zapasami** > **Zamówienia wychodzące** > **Zamówienie przeniesienia**.
2. W okienku akcji wybierz opcję **Nowy**.
3. Na karcie **Wiersze**, w skróconej karcie **Nagłówek zamówienia przeniesienia**, w sekcji **Przegląd**, w polu **Z magazynu** wybierz opcję **11**. W polu **Do magazynu** wybierz wartość **21**.
4. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia przeniesienia** wybierz pozycję **Dodaj**.
5. W polu **Numer pozycji** wybierz wartość **D0001**. W polu **Ilość przeniesienia** wpisz wartość **2**.
6. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** w sekcji **Handel zagraniczny** sprawdź, czy pole **Kod transakcji** jest ustawione automatycznie.
7. W okienku akcji na karcie **Wyślij** w grupie **Operacje** kliknij opcję **Wyślij zamówienie przeniesienia**.
8. W oknie dialogowym **Wysyłka**, na karcie **Przegląd** w polu **Aktualizuj** wybierz opcję **Wszystko**.
9. Kliknij przycisk **OK**, aby wysłać zamówienie.
10. W okienku akcji na karcie **Odbierz** w grupie **Operacje** wybierz pozycję **Przyjęcie**.
11. W oknie dialogowym **Przyjęcie**, na karcie **Przegląd** w polu **Aktualizuj** wybierz opcję **Wszystko**.
12. Kliknij przycisk **OK**, aby wysłać zamówienie.

#### <a name="transfer-the-transfer-order-to-the-intrastat-journal"></a>Przenieś zlecenie przelewu do dziennika Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw dla opcji **Zamówienie przeniesienia** wartość **Tak** i wszystkie inne opcje na wartość **Nie**.
4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat.

   ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie przeniesienia](media/intrastat_overview_3.png)

5.  Przejrzyj kartę **Ogólne** zamówienia przeniesienia.

    Zwróć uwagę, że pola w sekcjach **Wartość faktury** i **Wartość statystyczna** są ustawiane automatycznie. Wartości pól **Kwota faktury** i **Kwota statystyczna** są oparte na ustawieniach na stronie **Kody transakcji**. Wartość **20** w polu **Procent opłat** to wartość ustawiona na **stronie Zwolniony produkt**. Wartość w polu **Statystyczna kwota opłat** jest ilościowym wyrażeniem opłat (ponieważ wartość 107,24 oznacza 20 procent kwoty 536,18). Wartość pola **Wartość statystyczna** jest sumą wartości pól **Kwota statystyczna** i **Kwota opłat statystycznych**.

  ![Szczegóły zamówienia przeniesienia na karcie Ogólne na stronie Intrastat](media/intrastat_overview_4.png)

### <a name="additional-units"></a>Jednostki dodatkowe

W tym przykładzie firma w Niemczech musi zakupić 10 jednostek towaru od firmy we Włoszech. Oprócz kodów asortymentu dla tych towarów muszą zostać określone dodatkowe jednostki. W przykładzie pokazano sposób tworzenia nowych jednostek miary, przypisywania dodatkowych jednostek do kodu asortymentu Intrastat, księgować transakcje z dodatkowymi jednostkami oraz przeglądać arkusz Intrastat z ustawionym polem dodatkowych jednostek.

#### <a name="preliminary-setup"></a>Konfiguracja wstępna

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Organizacja** > **Firmy** i wybierz firmę **DEMF**.
2. Na skróconej karcie **Adres**, zweryfikuj czy w polu **Kraj/region** jest wartość **DEU(Niemcy)**.
3. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Handel zagraniczny** > **Parametry handlu zagranicznego**.
4. Na karcie **Intrastat**, na skróconej karcie **Ogólne**, w polu **Kod** **transakcji** wybierz wartość **11**.
5. Na skróconej karcie **hierarchii kodów asortymentu** w polu **Hierarchia kategorii** upewnij się, że wybrano pozycję **Intrastat**.
6. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Dostawcy** > **Wszyscy dostawy**.
7. W siatce zaznacz element **DE-001**.
8. Na skróconej karcie **Adres** wybierz pozycję **Edytuj**.
9. W oknie dialogowym **Edycja adresu** w polu **Kraj/region** wybierz pozycję **ITA**.
10. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

#### <a name="create-a-unit-of-measure"></a>Tworzenie jednostki miary

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Ustawienia** > **Jednostki** > **Jednostki**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Jednostka** wpisz nazwę jednostki miary. W tym przykładzie wpisz **GRM**.
4. Na skróconej karcie **Ogólne**, w sekcji **Klasyfikacja** w polu **Klasa jednostek** wybierz właściwość, dla których ma być mierzyna jednostka. W tym przykładzie wybierz wartość **Grupowe**.
5. W polu **System jednostek** wybierz system miar, do którego należy jednostka. Na przykład wybierz wartość **jednostki metryczne**.

#### <a name="set-up-unit-conversions"></a>Skonfiguruj konwersje jednostek

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Ustawienia** > **Jednostki** > **Konwersje jednostek**.
2. Na **karcie Konwersje między klasami** wybierz pozycję **Nowy**.
3. W oknie dialogowym **Konwersja jednostek** w polu **Produkt** wybierz wartość **F00007**.
4. W polu **Od jednostki** zaznacz opcję **każdy**.
5. W polu **Do jednostki** wybierz wartość **GRM**.
6. Sprawdź, czy współczynnik konwersji wynosi **1 = 1**.
7. Kliknij przycisk **OK**.
8. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
9. W siatce zaznacz element **F00007**.
10. Na skróconej karcie **Zarządzanie zapasami** w sekcji **Zapasy** w polu **Jednostka** wybierz **GRM**.
11. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="set-up-product-information"></a>Konfigurowanie informacji o produktach

1. Przejdź do **Zarządzanie informacjami o produktach** > **Produkty** > **Zwolnione produkty**.
2. W siatce zaznacz element **F00007**.
3. Na skróconej karcie **Handel zagraniczny**, w sekcji **Intrastat**, w polu **Asortyment** wybierz **920 20 34**.
4. Na okienku akcji wybierz opcję **Zapisz**.

#### <a name="assign-the-additional-unit-to-an-intrastate-commodity-code"></a>Przypisz dodatkową jednostkę do kodu asortymentu intrastate

1. Wybierz kolejno opcje **Zarządzanie informacjami o produktach** > **Ustawienia** > **Kategorie i atrybuty** > **Hierarchie kategorii**.
2. Na liście zaznacz element **Intrastat**.
3. W siatce zaznacz element **Głośnik**.
4. Na skróconej karcie **Handel zagraniczny** w polu **Jednostki dodatkowe** wybierz wartość **GRM**.
5. Na okienku akcji wybierz opcję **Zapisz**.

   Aby uzyskać więcej informacji, zobacz temat [Zarządzanie jednostkami miary](../../supply-chain/pim/tasks/manage-unit-measure.md).

#### <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W oknie dialogowym **Tworzenie zamówienia zakupu** w polu **Konto dostawcy** wybierz pozycję **DE-001**.
4. Kliknij przycisk **OK**.
5. Na karcie **Nagłówek** na skróconej karcie **Handel** **zagraniczny** sprawdź, czy w polu **Kod transakcji** znajduje się wartość **11**.
6. Na karcie **Wiersze**, na skróconej karcie **Wiersze zamówienia zakupu** w polu **Numer pozycji** wybierz wartość **F00007**. W polu **Ilość** wpisz wartość **10**.
7. Na skróconej karcie **Szczegóły wiersza**, na karcie **Handel zagraniczny** w sekcji **Handel zagraniczny** sprawdź, czy pole **Kod transakcji** i **Asortyment** są ustawione automatycznie.
8. W okienku akcji na karcie **Zakup** w grupie **Akcje** wybierz opcję **Potwierdź**.
9. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
10. W okienku akcji wybierz **Domyślne z**. W polu **Domyślna ilość dla wierszy** zaznacz wartość **Ilość zamówiona**. Następnie wybierz opcję **OK**.
11. Na skróconej karcie **Nagłówek faktury od dostawcy**, w sekcji **Identyfikacja faktury**, w polu **Numer** wprowadź wartość **VE-0010**.
12. W sekcji **Daty faktury**, w polu **Data faktury** wprowadź datę **5-10-2021** (5 października 2021.
13. W okienku akcji naciśnij przycisk **Zaksięguj**, aby zaksięgować fakturę

#### <a name="transfer-the-vendor-invoice-to-the-intrastat-journal"></a>Przeniesienie faktury od dostawcy do arkusza Intrastat

1. Wybierz kolejno opcje **Podatek** > **Deklaracje** > **Handel zagraniczny** > **Intrastat**.
2. W okienku akcji wybierz pozycję **Transfer**.
3. W oknie dialogowym **Intrastat (Przeniesienie)** ustaw opcję **Faktura od dostawcy** na wartość **Tak**.
4. Kliknij **OK**, aby przenieść transakcje, i przejrzyj arkusz Intrastat.

   ![W wierszu pokazane jest utworzone wcześniej na stronie Intrastat zamówienie zakupu](media/intrastat_overview_5.png)

5. Przejrzyj kartę **Ogólne** zamówienia zakupu. Należy zauważyć, że pola **Ilość dodatkowych jednostek** i **Jednostka dodatkowa** w sekcji **Jednostka** są ustawiane automatycznie.

   ![Szczegóły zamówienia zakupu na karcie Ogólne na stronie Intrastat](media/intrastat_overview_6.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
