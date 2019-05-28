---
title: Intrastat
description: Ten temat zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE). Omówiono proces sprawozdawczości oraz opisano wymagane ustawienia i warunki wstępne.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Intrastat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 28581
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: df02ce4ed43bc0cb1d2ff519c92ac41ca2983357
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1538250"
---
# <a name="intrastat"></a>Intrastat

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje o sprawozdawczości Intrastat o handlu towarami i — w niektórych przypadkach — usługami między krajami/regionami Unii Europejskiej (UE). Omówiono proces sprawozdawczości oraz opisano wymagane ustawienia i warunki wstępne.

Intrastat to system gromadzenia i generowania danych statystycznych na temat handlu towarami między krajami/regionami Unii Europejskiej (UE). Raport Intrastat jest wymagany w przypadku każdego produktu przekraczającego granicę innego kraju/regionu UE. W niektórych krajach/regionach obowiązek tworzenia raportów Intrastat dotyczy również usług. Na potrzeby raportów Intrastat mogą być gromadzone obowiązkowe i opcjonalne elementy. Wymagane są następujące elementy: identyfikator VAT podmiotu odpowiedzialnego za dostarczenie informacji, okres referencyjny, przepływ (przyjęcie lub wysyłka), ośmiocyfrowy kod towaru, kraj członkowski (kraj wysyłki i kraj docelowy), wartość towaru, ilość towaru (waga netto i jednostka dodatkowa) oraz charakter transakcji. Kraje/regiony mogą również gromadzić opcjonalne informacje w różnych warunkach. Do informacji opcjonalnych należą: kraj/region pochodzenia towaru, warunki dostawy, środek transportu, bardziej szczegółowy kod towaru niż 8-cyfrowy, kraj pochodzenia dla wysyłki i kraj pochodzenia dla odbioru, procedura statystyczna, wartość statystyczna, opis towaru oraz port/lotnisko załadunku/rozładunku.

## <a name="overview-of-the-intrastat-reporting-process"></a>Omówienie procedury raportowania Intrastat
W poniższych sekcjach opisano cały przebieg informacji używanych na potrzeby raportowania Intrastat.

### <a name="1-enter-a-transaction-that-crosses-the-border-of-another-eu-countryregion"></a>1. Podanie transakcji przekraczającej granicę innego kraju/regionu UE

Faktura dla odbiorcy, faktura niezależna, faktura zakupu, faktura projektu, dokument dostawy dla odbiorcy, dokument przyjęcia produktów od dostawcy lub zamówienie przeniesienia są przenoszone do arkusza Intrastat tyko wtedy, gdy kraj/region wysyłki lub dostawy znajduje się w **UE**. Ta funkcja została rozszerzona w Microsoft Dynamics 365 for Operations (wydanie 1611) i teraz pozwala określać adresy załadunku dla transakcji wewnątrzwspólnotowych. Jeżeli adres załadunku różni się od adresu służbowego dostawcy (lub adres służbowego odbiorcy w zamówieniu zwrotu), funkcja raportowania Intrastat użyje tych informacji. Podczas tworzenia zamówienia sprzedaży, faktury niezależnej, zamówienia zakupu, faktury od dostawcy, faktury projektu lub zamówienia przeniesienia, niektóre pola, które są powiązane z handlem zagranicznym, mają wartości domyślne w nagłówku dokumentu lub w wierszu. Domyślny kod transakcji jest pobierany z odpowiedniego pola na stronie **Parametry handlu zagranicznego**. Domyślny kod towaru, kraj/region pochodzenia i województwo pochodzenia są pobierane z pozycji. Można zmienić domyślne wartości i wprowadzić inne dane związane z handlem zagranicznym, takie jak procedura statystyczna, środek transportu i port.

### <a name="2-use-the-intrastat-journal-to-generate-information-about-trade-among-eu-countriesregions"></a>2. Używanie arkusza Intrastat do generowania i raportowania informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)

Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej. Można przenieść transakcje z faktury niezależnej, faktury dla odbiorcy, dokumentu dostawy, faktury od dostawcy, dokumentu dostawy dostawcy, faktury projektu lub zamówienia przeniesienia na podstawie kryteriów transferu ustawionych na stronie **Parametry handlu zagranicznego**. Można również ręcznie wprowadzić transakcje. W razie potrzeby można ręcznie zaktualizować przeniesione transakcje w arkuszu Intrastat. W określonych warunkach, które są ustawione na stronie **Kompresja Intrastat**, można kompresować transakcje w arkuszu Intrastat. W niektórych krajach/regionach można stosować niewielki próg wartości transakcji. Następnie transakcje poniżej tego progu można zgłaszać pod określonym kodem towaru. Kod towaru można zaktualizować w odpowiednich wierszach arkusza Intrastat, na podstawie ustawienia **dolnego limitu** na stronie **Parametry handlu zagranicznego**. Można także skompresować te transakcje na podstawie ustawienia **kompresji Intrastat**. Można sprawdzić poprawność transakcji w arkuszu Intrastat na podstawie ustawienia **Sprawdzenie ustawień** na stronie **Parametry handlu zagranicznego**. Można sprawdzić kompletność informacji w następujących polach: kraj/region, województwo, waga, kod towaru, kod transakcji, dodatkowe jednostki, port, pochodzenie, warunki dostawy, metody transportu i numer identyfikacji podatkowej. Transakcje niekompletne zostaną oznaczone jako nieprawidłowe.

### <a name="3-use-the-intrastat-journal-to-report-information-about-trade-among-eu-countriesregions"></a>3. Używanie arkusza Intrastat do zgłaszanie informacji dotyczących handlu między krajami/regionami Unii Europejskiej (UE)

Na potrzeby statystyczne co miesiąc generuje się dane dotyczące handlu między krajami/regionami Unii Europejskiej. Na podstawie ustawienia **Mapowanie formatu raportów** na stronie **Parametry handlu zagranicznego** można wydrukować raport Intrastat. Można również wygenerować plik elektroniczny na podstawie ustawienia **Mapowanie formatu plików** na stronie **Parametry handlu zagranicznego**. Aby dowiedzieć się więcej o raportowaniu Intrastat, w tym o warunkach wstępnych, obejrzyj nagrania zadań dotyczące raportowania Intrastat:

-   Generowanie unijnej deklaracji Intrastat
-   Przesyłanie transakcji do systemu Intrastat
-   Określanie adresu załadunku dla transakcji wewnątrzwspólnotowej

## <a name="prerequisites"></a>Wymagania wstępne
W następującej tabeli są podane wymagania wstępne dla raportowania Intrastat.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wymaganie wstępne</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ustawienia adresu</td>
<td>Konfigurowanie kodu ISO (International Organization for Standardization) dla krajów/regionów.</td>
</tr>
<tr class="even">
<td>Firma</td>
<td>Konfigurowanie numerów identyfikacji podatkowej do celów importu/eksportu, wewnętrznego numeru oddziału dla importu/eksportu i kodu Intrastat przypisanego do firmy.</td>
</tr>
<tr class="odd">
<td>Hierarchia kategorii produktów (hierarchia sprzedaży, hierarchia zaopatrzenia)</td>
<td>Przypisz kody asortymentu Intrastat do węzła kategorii na karcie <strong>Kody asortymentu</strong> na stronie <strong>Hierarchia kategorii</strong>. Po przypisaniu kodu asortymentu do węzła nadrzędnego kategorii, ten kod jest stosowany do wszystkich podrzędnych węzłów kategorii. Wybrane kody asortymentu będą dostępne w widoku <strong>Wybrane</strong> po wybraniu kodu asortymentu w szczegółach zwolnionego produktu i na zamówieniu sprzedaży, zamówienia zakupu oraz w wierszach zamówienia przeniesienia.</td>
</tr>
<tr class="even">
<td>Szczegóły zwolnionego produktu</td>
<td>Konfigurowanie następujących danych handlu zagranicznego dla zwolnionych produktów:
<ul>
<li><strong>Kod asortymentu</strong> — pozwala wybrać dowolną listę wybranych towarów pobraną z przypisanej kategorii produktów lub pełną listę kodów asortymentu Intrastat.</li>
<li><strong>Statystyczny procent sumy</strong></li>
<li><strong>Kraj/region pochodzenia</strong> — umożliwia wybór domyślnego kraju/regionu, w którym towary zostały w całości pozyskane lub wyprodukowane.</li>
<li><strong>Województwo pochodzenia/docelowe</strong> — pozwala wybrać domyślne województwo docelowe dla przyjęć i województwo pochodzenia dla wysyłki.</li>
<li><strong>Waga netto w kg</strong></li>
</ul></td>
</tr>
<tr class="odd">
<td>Odbiorcy</td>
<td>Konfigurowanie adresu dostawy w kraju/regionie UE dla odbiorcy.</td>
</tr>
<tr class="even">
<td>Dostawcy</td>
<td>Konfigurowanie adresu dostawcy w kraju/regionie UE.</td>
</tr>
<tr class="odd">
<td>Opłaty dodatkowe</td>
<td>Konfigurowanie kodu opłat dodatkowych w celu uwzględnienia kwoty faktury, kwoty statystycznej lub obu. Na stronie <strong>Kody opłat</strong> na karcie <strong>Handel zagraniczny</strong> włącz <strong>wartość faktury Intrastat</strong>, aby uwzględnić kwotę opłat w wartości faktury i włączyć <strong>Wartość statystyczna Intrastat</strong> w celu objęcia wartości statystycznej kwoty opłat dodatkowych.</td>
</tr>
<tr class="even">
<td>Raportowanie elektroniczne</td>
<td>Ustawienie konfiguracji raportu elektronicznego do eksportowania danych Intrastat do pliku w formacie żądanym przez odpowiednie organy i podglądu danych Intrastat w formacie przyjaznym dla użytkownika, który daje się odczytać (np. plik programu Microsoft Excel).</td>
</tr>
<tr class="even">
<td>Magazynowanie</td>
<td>Skojarz konta dostawców z kodami magazynu w celu uzupełnienia numeru identyfikacji podatkowej przy przesyłaniu zamówienia przeniesienia.</td>
</tr>
</tbody>
</table>

## <a name="setup"></a>Konfiguracja
W poniższych sekcjach opisano ustawienia, które są wymagane na potrzeby raportowania Intrastat.

### <a name="set-up-all-required-intrastat-related-lists"></a>Ustaw wszystkie wymagane listy związane z deklaracją Intrastat

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Lista</th>
<th>Informacje dodatkowe</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kody asortymentu</td>
<td>Skonfiguruj hierarchię kategorii typu <strong>kod asortymentu</strong>i wprowadź wszystkie kody asortymentu zgodnie z listą. Dla każdego towaru należy zdefiniować następujące informacje:
<ul>
<li>Nazwa i kod towaru</li>
<li>Przyjazna nazwa lub przetłumaczona nazwa</li>
<li>Ustawienia raportowania dodatkowych (uzupełniających) jednostek na karcie <strong>Handel zagraniczny</strong>. Można wybrać dodatkowe jednostki z listy. Można również określić, czy oprócz wybranej jednostki dodatkowej należy podać wagę towarów.</li>
</ul></td>
</tr>
<tr class="even">
<td>Kody transakcji</td>
<td>Ustaw charakter transakcji zgodnie z wymaganiami danego kraju/regionu. Dla każdego ustawionego kodu transakcji należy skonfigurować reguły obliczania kwot faktur i kwot statystycznych dla zamówień sprzedaży/zakupu i zamówień przeniesienia.
<ul>
<li>Dla zamówień przeniesienia należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:
<ul>
<li><strong>Puste</strong> – kwota będzie równa 0 (zero).</li>
<li><strong>Wartość finansowa</strong> – kwota będzie równa kosztowi finansowemu.</li>
<li><strong>Łączny koszt</strong> – kwota będzie równa łącznemu kosztowi transakcji.</li>
<li><strong>Ręcznie</strong> – kwota będzie równa kwocie ręcznie określonej w wierszu zamówienia przeniesienia.</li>
</ul></li>
<li>Dla zamówień sprzedaży i zakupu należy zdefiniować jedną z następujących reguł obliczania kwot faktur i kwot statystycznych:
<ul>
<li><strong>Puste</strong> – kwota będzie równa 0 (zero).</li>
<li><strong>Kwota faktury</strong> – kwota będzie równa kwocie fakturowana dla towaru.</li>
<li><strong>Kwota podstawy</strong> – kwota będzie równa kwocie, która zostałaby zafakturowana przed zastosowaniem rabatów.</li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td>Metody transportu</td>
<td>Ustaw tryb transportu zgodnie z wymaganiami danego kraju/regionu. Dla każdej metody dostawy można skonfigurować domyślną metodę transportu na karcie <strong>Handel zagraniczny</strong>.</td>
</tr>
<tr class="even">
<td>Porty</td>
<td>Skonfiguruj port/lotnisko załadunku/rozładunku, jeśli te informacje są gromadzone w danym kraju/regionie.</td>
</tr>
<tr class="odd">
<td>Procedury statystyczne</td>
<td>Ustaw procedury statystyczne, jeśli te informacje są gromadzone w danym kraju/regionie.</td>
</tr>
</tbody>
</table>

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
<li>Domyślne kody transakcji dla zamówień sprzedaży, zamówień zakupu, faktur korygujących i zamówień przeniesienia. Kod transakcji ustawiony dla faktur korygujących jest również używany jako kod zwrotu towarów fizycznych i jest używany do obsługi odchyleń zwrotów towarów fizycznych względem faktur korygujących.</li>
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

