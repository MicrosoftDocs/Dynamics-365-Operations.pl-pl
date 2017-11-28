---
title: "Zarządzanie projektami i ich księgowanie"
description: "Funkcji zarządzanie projektami i ich księgowania można używać w wielu branżach w celu świadczenia usług, wytwarzania produktów lub uzyskiwania rezultatów."
author: KimANelson
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3a1bfd4bd5f396c05277159ac112eaa8197d5818
ms.openlocfilehash: 6a2c51d9ffe288dad2db43ecd0a4c8f717c6379a
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="project-management-and-accounting"></a>Zarządzanie projektami i ich księgowanie

[!include[banner](../includes/banner.md)]


Funkcji zarządzanie projektami i ich księgowania można używać w wielu branżach w celu świadczenia usług, wytwarzania produktów lub uzyskiwania rezultatów.  

Projekt to grupa działań mających na celu dostarczenie usługi, wytworzenie produktu lub osiągniecie celu. Projekty zużywają zasoby i generują wyniki finansowe w formie przychodów lub aktywów.

## <a name="projects-across-industries"></a>Projekty różnych branż
Funkcje zarządzania projektami i księgowania można wykorzystywać w różnych branżach, jak pokazano na poniższej ilustracji. [![Projekty w różnych branżach](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

W biurze obsługi można użyć biletu do opisania zestawu działań wymaganych do rozwiązania zgłoszonego problemu. Firmy konsultingowe, takie jak organizacje zarządzające, reklamowe lub świadczące usługi w zakresie porad technicznych, nazywają swoje działania projektami. W marketingu kampania oznacza pakiet pracy, która musi zostać dostarczona. W produkcji na podstawie projektu, zlecenie produkcyjne dotyczy różnych prac, które muszą być wykonane w celu wyprodukowania gotowego towaru. Niezależnie od nazwy tych projektów, obejmują one zasoby, harmonogramy i koszty, a funkcje zarządzania projektem i księgowania w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition pomagają w planowaniu, wykonaniu i analizie tych projektów.

## <a name="project-phases"></a>Fazy projektu
Mimo że przebieg poniższego procesu jest ukierunkowany na projekty zewnętrzne lub projekty realizowane dla jednego lub kilku odbiorców, funkcja ma także zastosowanie do wewnętrznych projektów dotyczących tylko kosztów. 

![3 etapy projektu](./media/3-stages-of-a-project.png) 

Jak pokazano na poprzedniej ilustracji, zarządzanie projektami i ich księgowanie można podzielić na trzy fazy:

1.  Inicjowanie
2.  Wykonaj
3.  Analizuj

## <a name="initiate-the-project"></a>Inicjowanie projektu
Przy uruchamianiu projektu występuje kilka kluczowych procesów. Za pomocą ofert w ramach projektu można informować odbiorcę o szacowanej robociźnie, wydatkach i materiałach. Można rejestrować warunki fakturowania, limity i porozumienia w ramach umowy dotyczącej projektu. Struktura podziału pracy (SPP) umożliwia planowanie i szacowanie pracy. Jako wytyczne wykonania projektu można ustawić prognozy i budżety. Poniższa ilustracja pokazuje strukturę projektu.[![struktura projektu](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Utwórz oferty w ramach projektu

W fazie początkowej sprzedaży projektu, oferty w ramach projektu umożliwiają przedstawienie odbiorcy niewiążącej oferty. Oferta może obejmować wiele elementów, na przykład oferowane towary i usługi, podstawowe informacje kontaktowe, specjalne umowy handlowe i rabaty oraz możliwe podatki i dopłaty.

Można także wystawić poręczenie dla transakcji oferty w ramach projektu między Twoją organizacją a odbiorcą. Po utworzeniu oferty w ramach projektu możesz tworzyć żądania poręczenia dla odbiorcy i przesłać je do banku. Gdy bank zatwierdza żądanie, zostaje wystawione poręczenie dla odbiorcy. 

Aby uzyskać więcej informacji, zobacz [Oferty w ramach projektu](project-quotations.md).

### <a name="create-project-contracts"></a>Tworzenie umów dotyczących projektów

Po zawarciu umowy z odbiorcą lub innym źródłem finansowania w celu realizacji projektu musisz najpierw utworzyć umowę dotyczącą projektu. Następnie podczas tworzenia projektu, należy przypisać go do odpowiedniej umowy. Typ projektu tworzonego dla umowy dotyczącej projektu określa metodę wystawiania faktur dla klientów projektu. Umowę dotyczącą projektu i powiązany projekt można zmienić, ale nie można zmienić typu projektu. Aby uzyskać więcej informacji dotyczących typów projektów zobacz sekcję "Tworzenie projektów".

Aby uzyskać więcej informacji o umowie dotyczącej projektu, zobacz [Umowy dotyczące projektu](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Tworzenie struktury podziału pracy

Stopień szczegółowości w SPP zależy od poziomu dokładności, jaki jest wymagany w szacunkach i poziomu śledzenia, który jest wymagany dla tych oszacowań. Projektów o bardzo małej tolerancji na opóźnienia harmonogramu czy wahania kosztów zazwyczaj wymagają bardziej szczegółowych SPP i dokładnego monitorowania postępów pracy i kosztów względem SPP. 

Aby uzyskać więcej informacji, zobacz [Struktury podziału pracy](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Tworzenie prognoz i budżetów projektów

Korzystaj z prognozowania projektu, jeśli Twoja organizacja ma perspektywę organizacyjną i koncentruje się przychodach i kosztach pochodzących z określonych transakcji. Korzystaj z budżetowania projektu, jeśli Twoja organizacja bardziej koncentruje się na kwotach finansowych. Każda metoda ma swoje zalety. Aby uzyskać więcej informacji, zobacz [Budżety i prognozy projektu](project-forecasts-budgets.md).

### <a name="create-projects"></a>Tworzenie projektów

W programie Finance and Operations można utworzyć sześć typów projektów. W każdym z nich inaczej konfiguruje się rozpoznanie kosztów i przychodów. Wybrany typ projektu zależy od przeznaczenia projektu. W poniższej tabeli opisano typowe użycie każdego typu projektu.

                                                                                                                                                                         |
| Typ projektu      | Opis                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Czas i materiały | W projektach czasowych i materiały odbiorcy wystawiany jest rachunek obejmujący wszystkie koszty poniesione w ramach projektu. Te koszty obejmują godziny, wydatki, towary i opłaty.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Stała cena       | W projektach o stałej cenie faktury zawierają transakcje akonto. Projekt o stałej cenie jest fakturowany na podstawie harmonogramu opartego na umowie dotyczącej projektu. Przychód dla projektu o stałej cenie może być obliczany i księgowany przez cały okres trwania projektu przy użyciu metody procentu ukończenia. Można też obliczać i księgować przychód po zakończeniu projektu przy użyciu metody zakończonego kontraktu. Przedsiębiorstwa często korzystają z wartości prac w toku (PWT) do obliczania stopnia ukończenia projektu lub grupy projektów.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Inwestycje        | Projekty inwestycyjne to projekty, które nie przynoszą natychmiastowych dochodów. Zazwyczaj są używane w przypadku długoterminowych projektów wewnętrznych, w których koszty muszą być kapitalizowane. Dla projektów inwestycyjnych można rejestrować tylko koszty towarów, godziny i wydatki. Koszty w projekcie inwestycyjnym są śledzone i kontrolowane za pomocą funkcji szacowania. Projekty inwestycyjne można konfigurować z opcjonalnym maksymalnym limitem kapitalizacji. W miarę postępów projektu inwestycyjnego rejestrowane są jego koszty na kontach kosztów PWT, gdzie koszty są wstrzymane aż do ukończenia projektu. Po wyeliminowaniu projektu wartość PWT jest przenoszona do środka trwałego, na konto księgowe czy do nowego projektu. Uwaga: Transakcje w projektach inwestycyjnych nie są wyświetlane na stronach **Księgowanie kosztów**, **Naliczanie przychodów** ani **Tworzenie propozycji faktur**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| Projekt kosztów      | Podobnie jak w projektach inwestycyjnych, projekty kosztów są zwykle używane do śledzenia projektów wewnętrznych i tylko godziny, wydatki i towary mogą być rejestrowane w projektach kosztów. Projekty kosztów są zwykle określane na okres krótszy niż projekty inwestycyjne. Dodatkowo, w przeciwieństwie do projektów inwestycyjnych projekty kosztów nie mogą być kapitalizowane na kontach bilansowych. Zamiast tego transakcje projektowe są księgowane tylko na kontach zysku i straty. **UWAGA** Transakcje w projektach kosztów nie są uwzględniane na stronach **Księgowanie kosztów**, **Naliczanie przychodów** ani **Tworzenie propozycji faktur**. Ponieważ projekty kosztowe są zazwyczaj używane do śledzenia projektów wewnętrznych, zwykle nie muszą one być skojarzone z kontem odbiorcy. Jednak jeśli konfiguracja wymaga, aby dla zamówień zakupu można tworzyć zapotrzebowanie na towary, należy skojarzyć projekt kosztowy z odbiorcą. Jest to spowodowane tym, że zapotrzebowania na towary są zarządzane jako wiersze zamówienia sprzedaży, a system wymaga określenia odbiorcy. Jednak ta konfiguracja nie spowoduje automatycznego tworzenia zapotrzebowania na towary na podstawie zamówienia zakupu. W przypadku projektów kosztów ustawienie **tworzenie zapotrzebowania na towary** jest ignorowane. Jeśli jest potrzebne zapotrzebowanie na towary w projektach kosztowych, możesz utworzyć je ręcznie, o ile odbiorca jest skojarzony z projektem. |
| Wewnętrzne          | Projekty wewnętrzne służą do śledzenia kosztów w projekcie, który jest wewnętrzny w danej organizacji. Projekty wewnętrzne mogą dostarczać narzędzia planowania do zarządzania zużyciem zasobów. **Note:** Transakcje w projektach wewnętrznych nie są uwzględniane na stronach **Naliczanie przychodów** ani **Tworzenie propozycji faktur**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Godzina              | Projekty czasowe służą do śledzenia czasu skojarzonego z niepłatnymi i i nieproduktywnymi działaniami, takimi jak projekt śledzenia zwolnień dla pracowników. Transakcje w projektach typu czas nie są księgowane w księdze. Zamiast tego są uwzględniane w raportach wykorzystania pracownika. Tylko transakcje godzinowe mogą być rejestrowane w projektach czasowych. Arkusz godzin lub karta czasu pracy służy do rejestrowania tych godzin w projekcie. Po zarejestrowaniu godzin są one wyświetlane w postaci transakcji projektu, ale nie mają odpowiadających transakcji na załączniku. **Uwaga:** Transakcje w projektach czasowych nie są uwzględniane na stronach **Księgowanie kosztów**, **Naliczanie przychodów** ani **Tworzenie propozycji faktur**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |


### <a name="assign-workers-categories-and-resources"></a>Przypisywanie pracowników, kategorii i zasobów

Można planować zasoby pracowników w oparciu o wymagania i harmonogram projektu lub o umiejętności i dostępność pracowników. Używając funkcji planowania zasobów, można wydajnie i efektywnie rozdzielać pracowników organizacji. Można szybko znaleźć najbardziej wykwalifikowanych pracowników, którzy są dostępni do pracy nad projektem. Można także łatwo zobaczyć, jak efektywniej wykorzystać tych pracowników podczas trwania projektu. 

Poniżej przedstawiono sposoby wykorzystania funkcji planowania zasobów:

-   Informacje o atrybutach pracownika, takich jak wykształcenie, umiejętności, certyfikaty, doświadczenie w projekcie, umożliwiają dopasowanie pracownika do wymagań dotyczących projektu.
-   Informacje dotyczące kalendarza pracownika i dostępności umożliwiają dopasowanie harmonogramu pracownika do kalendarza projektu.
-   Przegląd zdolności produkcyjnych pracowników i określenie sposobu używania tych zdolności produkcyjnych. Na przykład, jeśli pracownik nie jest w pełni wykorzystany, można go przypisać do projektu, który pasuje do dostępności i atrybutów pracownika.
-   Przegląd dostępności pracownika, aby upewnić się, że nie występują żadne konflikty kalendarza z przypisaniami pracownika.
-   Przegląd informacji o wykorzystaniu pracownika w ujęciu sumarycznym, np. według działu lub pracownika, lub w widoku szczegółowym, np. wg pracowników w dziale lub tygodniowych szczegółów dla każdego pracownika.
-   Modyfikowanie przydziałów zasobów dla różnych jednostek czasu, takich jak dzień, tydzień lub miesiąc, aby zoptymalizować wykorzystanie pracowników.

## <a name="execute-the-project"></a>Realizacja projektów
W czasie wykonywania projektu członkowie zespołu i menedżerowie rejestrują pracę i poniesione wydatki przy użyciu kart czasu pracy, raportów wydatków i innych dokumentów biznesowych. Menedżerowie projektu korzystają z narzędzi do śledzenia wykorzystania kwot budżetu projektu. Menedżerowie projektów mogą również zamawiać, pobierać lub dostarczać materiały do projektów za pomocą zamówień zakupu i innych dokumentów biznesowych. Faktury są przygotowane i zatwierdzane, tak aby można było wystawiać faktury dla odbiorców za pracę w toku. Na koniec tego procesu szacowany jest przychód i uwzględniany w finansach organizacji.

### <a name="manage-work-breakdown-structures"></a>Zarządzanie strukturą podziału pracy

SPP to opis pracy, która zostanie wykonana w ramach projektu. Struktura podziału pracy jest hierarchią zadań. Reprezentuje ona nie tylko pracę dla każdego zadania, ale również zakres, koszt i czas trwania zadania. 

Aby uzyskać więcej informacji, zobacz [Struktury podziału pracy](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Zarządzanie prognozami i budżetami projektów

Obsługa i kontrola projektów jest możliwa na dwa sposoby: za pomocą prognoz projektów i budżetów projektów. Korzystaj z prognozowania projektu, jeśli Twoja organizacja ma perspektywę organizacyjną i koncentruje się przychodach i kosztach pochodzących z określonych transakcji. Korzystaj z budżetowania projektu, jeśli Twoja organizacja bardziej koncentruje się na kwotach finansowych.

Aby uzyskać więcej informacji, zobacz [Budżety i prognozy projektu](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Tworzenie zlecenia produkcyjnego

Zlecenie produkcyjne związane z projektem może być połączone z zamówieniem sprzedaży lub zapotrzebowaniem na towar przy użyciu metody towaru gotowego lub metody towaru zużytego. Ponadto, jeśli zlecenie produkcyjne zostało utworzone ręcznie, nie ma żadnego połączenia między zleceniem produkcyjnym i zamówieniem sprzedaży lub zapotrzebowaniem na towary (brak połączenia z zamówieniem). Ale w przypadku automatycznego utworzenia zlecenia produkcyjnego w celu zrealizowania zamówienia sprzedaży lub zapotrzebowaniem na towar, istnieje powiązanie między zleceniem produkcyjnym i zamówieniem sprzedaży lub zapotrzebowaniem na towary (łącze do zamówienia). 

Na podstawie kombinacji tych czynników, użyj jednej z następujących metod:

-   **Towar gotowy/Połączenie z zamówieniem** – powiąż projekt z zamówieniem sprzedaży lub zapotrzebowaniem na towar. W wypadku tej metody rzeczywiste koszty projektu są księgowane po zaksięgowaniu zamówienia sprzedaży lub po zaktualizowaniu dokumentu dostawy, z uwzględnieniem zapotrzebowania na towar. Koszty zostaną zaksięgowane jako towar gotowy.
-   **Towar gotowy/bez połączenia z zamówieniem** — koszty rzeczywiste nie mogą być zaksięgowane, aż cykl produkcyjny towaru będzie miał stan **Zakończono**. Koszty towaru gotowego są księgowane w ramach jednej transakcji.
-   **Towar zużyty/Połączenie z zamówieniem** – powiąż projekt z zapotrzebowaniem na towar. Dzięki tej metodzie można przejrzeć rzeczywiste koszty projektu, gdy produkcja ma stan **Rozpoczęte** lub gdy jest zgłoszona jako gotowa. Koszty zostaną zaksięgowane jako wiele transakcji towarów projektu odnoszących się do surowców i godzin zużytych w ramach produkcji. Po zaktualizowaniu dokumentu dostawy, z uwzględnieniem zapotrzebowanie na towar, koszty projektowe nie są księgowane. Można zdefiniować poziom hierarchii listy składowej (BOM), przy którym powinny być śledzone projekty w ramach produkcji.
-   ****Towar zużyty/brak połączenia z zamówieniem**** — powiąż projekt z zapotrzebowaniem na towar. Dzięki tej metodzie można przejrzeć rzeczywiste koszty projektu, gdy produkcja ma stan **Rozpoczęte** lub gdy jest zgłoszona jako gotowa. Koszty zostaną zaksięgowane jako wiele transakcji towarów projektu odnoszących się do surowców i godzin zużytych w ramach produkcji. Można zdefiniować poziom hierarchii listy składowej (BOM), przy którym powinny być śledzone projekty w ramach produkcji.

### <a name="procure-products-and-services"></a>Zaopatrzenie w produkty i usługi

Zakup i sprzedaż towarów są dominującymi działaniami firmach skoncentrowanych na projekcie.

#### <a name="purchase-orders-for-projects"></a>Zamówienia zakupu dla projektu

Cel zamówienia zakupu wyznacza termin realizacji zamówienia zakupu, a w konsekwencji termin uwzględnienia towarów w projekcie.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metoda</th>
<th>Cel</th>
<th>Zużycie towarów</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Utwórz bezpośrednio zamówienie zakupu.</td>
<td>Zakup u zewnętrznego dostawcy w celu zużycia w projekcie. Zamówienie zakupu można utworzyć w następujący sposób:
<ul>
<li>Z samego projektu. W tym przypadku projekt jest już zdefiniowany dla zamówienia zakupu.</li>
<li>Przechodząc do zamówienia zakupu projektu. Należy wybrać zarówno dostawcę, jak i projekt, dla których zostanie utworzone zamówienie zakupu.</li>
</ul></td>
<td>Towary są zużywane przy aktualizacji faktury dostawcy.</td>
</tr>
<tr class="even">
<td>Tworzenie zamówienia zakupu na podstawie zamówienia sprzedaży.</td>
<td>Kupowanie towarów podczas tworzenia zamówienia sprzedaży z projektu.</td>
<td>Towary są zużywane, gdy zamówienie sprzedaży jest fakturowane do odbiorcy.</td>
</tr>
<tr class="odd">
<td>Tworzenie zamówienia zakupu z zapotrzebowania na towar.</td>
<td>Kupowanie towarów podczas tworzenia zapotrzebowania na towary z projektu.</td>
<td>Towary są zużywane przy aktualizacji dokumentu dostawy dla zapotrzebowania na towar.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Zamówienia sprzedaży dla projektów

W zarządzaniu projektami księgowaniu można rejestrować zużycie towarów na różne sposoby. Można sprzedawać lub kupować towary z projektu, albo rezerwować towary dla projektu. 

Można zamówić towary z magazynu firmy do zużycia w projekcie. Można też kupować towary u zewnętrznego dostawcy. Towary mogą być zużywane w przypadku wszystkich typów projektów z wyjątkiem projektów typu czas. 

Sposób zamawiania towarów zależy od tego, skąd się je zamawia:

-   Aby zamówić towary z magazynu firmy, trzeba utworzyć zamówienie jako zapotrzebowanie na towary. W przypadku użycia strony **Zapotrzebowanie na towary** można tak skonfigurować zapotrzebowanie, aby odbierać towary jako dostawy częściowe. Dzięki temu można odłożyć zużycie pewnej ilości towarów do czasu, gdy te towary będą wymagane.
-   W przypadku zamawiania towarów u dostawcy zewnętrznego trzeba utworzyć zamówienie zakupu na stronie **Zamówienie zakupu**.

> [!NOTE] 
> Nie można anulować dokumentu dostawy dla zamówienia sprzedaży związanego z projektem, jeśli towary zostały już zaznaczone do pakowania. 

W poniższej tabeli wymieniono metody zamawiania towarów i opisano sposób wykorzystania towarów.

| Metoda            | Cel                                                                                                                                                        | Zużycie w transakcjach dotyczących pozycji                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Zamówienie sprzedaży       | Wprowadzenie transakcji sprzedaży bezpośrednio w projekcie typu czas i materiały.                                                                                                   | Transakcje towarowe są zużywane w momencie zaksięgowania faktury odbiorcy.                                                                               |
| Arkusz magazynowy | Wprowadź i obsługuj rekordy towaru szybko. Jeśli na przykład użytkownik chce wprowadzić zapotrzebowanie na towary na podstawie wydrukowanej listy, może zastosować arkusz magazynowy. | Transakcje towarowe są zużywane w momencie zaksięgowania arkusza.                                                                                        |
| Zapotrzebowanie na pozycje  | Wprowadź towary, które nie zostaną zużyte natychmiast. Ta metoda umożliwia użytkownikom śledzenie liczby towarów zużytych w ramach jednego rekordu zapotrzebowania na towary.    | Transakcje towarowe są zużywane w momencie zaktualizowania dokumentu dostawy. Oznacza to, że zapotrzebowanie na towary jest tworzone w momencie zaksięgowania dokumentu dostawy. |
| Zamówienia zakupu   | Wprowadź transakcje w jednej z trzech lokalizacji, zależnie od metody zakupu.                                                                              | Transakcje towarowe są zużywane w momencie zaktualizowania dokumentu dostawy albo utworzenia faktury dla odbiorcy lub dostawcy.                                      |

### <a name="process-project-invoices"></a>Przetwarzanie faktur dotyczących projektu

Typ projektu określa, która procedura fakturowania powinna zostać zastosowana. Tylko dwa typy projektów zewnętrznych, czas i materiały oraz o stałej cenie, mogą być fakturowane. Projekty typu czas i materiały oraz projekty o stałej cenie są zawsze dołączane do umowy dotyczącej projektu. 

Przed utworzeniem faktury odbiorcy dla projektu, można utworzyć fakturę wstępną lub propozycję faktury. W propozycji faktury można wybrać transakcje projektu, które zostaną uwzględnione na fakturze projektu. Można również przejrzeć szczegóły faktury przed zaksięgowaniem faktury projektu i wysłać ją do odbiorcy lub źródła finansowania. 


Aby uzyskać więcej informacji dotyczących przetwarzania faktur w projekcie, zobacz [Fakturowanie projektu](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Obliczanie kosztu do zakończonego projektu

Podczas tworzenia oszacowania można wybrać metodę, która jest używana do obliczania kosztu ukończenia projektu. Wybierz metodę w polu **Metoda Koszt do zakończenia** na stronie **Tworzenie oszacowania**. Wybrana metoda będzie stosowana osobno w wierszach kosztów szacowania kosztów. Gdy wiersz ma stan **Utworzone**, można zmienić metodę stosowaną do niego na stronie **szacowania kosztów**. 

W poniższej tabeli opisano metody obliczania kosztu zakończenia projektu.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Metoda</th>
<th>Opis</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Łączny koszt — rzeczywisty</td>
<td>Szacowane koszty należy wprowadzić ręcznie. Po wypełnieniu kolumn <strong>łączny koszt</strong> lub <strong>całkowita ilość</strong> na stronie <strong>szacowania kosztów </strong>koszty rzeczywiste są odejmowane od wartości wprowadzonych przez użytkownika. Wynik jest kosztem zakończenia projektu. Na ogół postęp kosztów nie jest śledzony na podstawie, na przykład liczby noclegów hotelowych i posiłków, które są rejestrowane w każdym okresie. zamiast. Śledzenie jest zazwyczaj oparte na porównaniu względem łącznej kwoty za szacowane godziny. To podejście nie wymaga modelu prognozy, a całkowity koszt lub całkowitą ilość można zmienić ręcznie. Po wprowadzeniu wartości w kolumnie <strong>łączny koszt</strong> lub <strong>całkowita ilość</strong> program Finance and Operations porównuje tę wartość względem rzeczywistych transakcji zaksięgowanych w danym okresie, a następnie zmniejsza wartość w kolumnie <strong>ilość do zakończenia</strong> lub <strong>koszt do zakończenia</strong>.</td>
</tr>
<tr class="even">
<td>Łączny budżet — rzeczywisty</td>
<td>Koszty rzeczywiste są porównywane z modelem prognozy wybranym do określenia kosztu. Ta metoda korzysta z modelu łącznego budżetu, zawierającego prognozowane transakcje. Aby uzyskać dokładniejszy widok projektu, można dostosować modelu budżetu, gdy projekt jest w toku. W razie konieczności korekty prognozy należy wykonać poniższy proces ogólny:
<ol>
<li>Skopiuj prognozowane transakcje do innego modelu prognozy.</li>
<li>Porównaj prognozowane transakcje z rzeczywistymi.</li>
<li>Zachowaj, zmniejsz lub zwiększ oszacowania dla następnego okresu.</li>
</ol>
Program Finance and Operations nie zmniejsza automatycznie prognozowanych oszacowań. Dlatego warto zachować pierwotny model prognozy w projekcie o stałej cenie, aby mieć podstawę do porównania, gdy projekt zostanie zakończony. 
> [!NOTE] Po wybraniu tej metody należy użyć co najmniej dwóch modeli prognoz. Jeden model powinien zawierać pierwotną prognozę. Dla innego modelu należy skopiować transakcje prognozy z innego modelu. Ta metoda dotyczy tylko projektów o stałej cenie i inwestycyjnych.</td>
> </tr>
<tr class="odd">
<td>Pozostały budżet</td>
<td>Ta metoda wykorzystuje model pozostałego budżetu, aby obliczyć koszt ukończenia projektu. W przypadku korzystania z tej metody koszty rzeczywiste i prognozowane kwoty w modelu pozostałego budżetu są sumowane. Wynikiem jest całkowity koszt. Przed użyciem tej metody model pozostałego budżetu musi mieć możliwość odliczenia transakcji dla rzeczywistych transakcji, które są zarejestrowane w systemie. Na stronie <strong>Modele prognoz</strong> upewnij się, że pola są oznaczone w grupie <strong>Automatyczne zmniejszenie prognozy</strong>. Na ogół pozostały budżet jest kopiowany z pierwotnego budżetu. Ponieważ transakcje zostały wprowadzone, transakcje w pozostałym budżecie są zmniejszane. W miarę realizacji projektu, jeśli określisz, że pozostały budżet musi zostać skorygowany, zmieniasz transakcje prognozy na pozostały budżet. <strong>Uwaga:</strong> Ta metoda może zostać zastosowana tylko, jeśli model prognozy jest dołączony do szacowania.</td>
</tr>
<tr class="even">
<td>Jak poprzednie szacowanie</td>
<td>Stosowana jest ta sama metoda szacowania, która została użyta w poprzednim okresie. Ta metoda wymaga modelu prognozy, jeżeli poprzedni okres wymagał modelu prognozy.</td>
</tr>
<tr class="odd">
<td>Ustaw koszt do zakończenia na zero</td>
<td>Zazwyczaj ta metoda jest używana przed wyeliminowaniem szacowanego projektu. Ta metoda pasuje do oszacowania sum z rzeczywistymi transakcjami, które zostały zaksięgowane i usuwa dane w kolumnie <strong>Koszt do zakończenia</strong>. Otrzymany procent ukończenia zawsze wynosi 100%. Pole <strong>Prognoza</strong> nie jest wybrane dla każdego tworzonego wiersza kosztów, a szacowana suma jest kopiowana z poprzedniego szacowania kosztów. Rzeczywiste zużycie dla okresu szacowania jest odliczane od kosztu do zakończenia projektu. Ta metoda nie wymaga modelu prognozy.</td>
</tr>
<tr class="even">
<td>Z szablonu kosztów</td>
<td>Stosowana jest metoda kosztu do zakończenia skonfigurowana w szablonie kosztu skojarzonym z wybranym projektem szacunkowym.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analizowanie projektu
Na najbardziej podstawowym poziomie projekt jest używany do grupowania transakcji rejestrujących koszty i księgowania tych kosztów w księdze głównej. 

Ogólnie rzecz biorąc, transakcje te są wynikiem dokumentów biznesowych, takich jak karty czasu pracy, raporty z wydatków, faktury od dostawcy lub transakcje magazynowe. Zazwyczaj cykl życia projektu rozpoczyna się od szacunki, prognoz i budżetów, które pomagają w planowaniu i przewidywaniu pracy oraz wpływu finansowego projektu. Podczas analizy projektu można ocenić nie tylko transakcje, które wystąpiły w trakcie projektu, ale również dokładność oszacowania i prognoz, stawki wykorzystania członków zespołu projektu i ogólny sukces projektu.

### <a name="analyze-cash-flow"></a>Analiza przepływu gotówki

Za pomocą monitorowania przepływów pieniężnych można kontrolować zarówno prognozowane, jak i rzeczywiste przepływy gotówkowe dla projektu. Można kontrolować przepływy pieniężne w trakcie projektu, a także wyświetlać ich stan po ukończeniu projektu. 

Monitorują przepływy pieniężne, można ocenić konkretny projekt, korzystać z raportów w celu kontroli wielu projektów i przenosić przepływy pieniężne projektu do prognoz w księdze głównej.

#### <a name="cash-inflow-forecasting"></a>Prognozowanie przepływów pieniężnym

Na podstawie konfiguracji można prognozować wpływy gotówki dla wybranego projektu. Na przykład, jeśli datą projektu jest 5 marca 2012 roku, a faktura ma zostać wystawiona 31 marca 2012 roku, oto jak można przewidzieć termin realizacji i datę oczekiwanej płatności za sprzedaż

-   **Data projektu:** 5 marca 2012.
-   **Data faktury:** 31 marca 2012. Ta data jest ustalana w oparciu o częstotliwość faktur. W tym przykładzie ustawia się częstotliwość faktury na bieżący miesiąc. W związku z tym wszystkie, które są księgowane w marcu są fakturowane w ostatnim dniu miesiąca.
-   **Data wykonania:** 14 kwietnia 2012 r. Ta data jest ustalana na podstawie warunków płatności ustawionych dla projektu. W tym przykładzie zaznaczono warunki płatności 14 dni. W związku z tym 14 dni dodaje się do daty faktury, by otrzymać termin realizacji 14 kwietnia 2012.
-   **Data oczekiwanej płatności za sprzedaż:** 27 kwietnia 2012 r. Data ta jest obliczana przez dodanie liczby dni w polu **Ogólne dni buforowe** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** do liczby dni w polu **Indywidualne dni buforowe** na stronie **Umowy dotyczące projektu**, a następnie dodane do całkowitej liczby dni w polu **Data wykonania**. Na przykład wprowadzono **3** w polu **ogólne dni buforowe** i **10** w polu **indywidualne dni buforowe**. W związku z tym 13 dni dodaje się do terminu, oczekiwany termin płatności 27 kwietnia 2012 r.

Ogólne dni buforowe mogą zastąpić indywidualne dni buforowe lub zostać dodane do indywidualnych dni buforowych:

-   Aby użyć funkcji Ogólne dni buforowe jako zamiennika indywidualnych dni buforowych, wprowadź średnią liczbę dni między datą płatności a rzeczywistą datą płatności dla odbiorców.
-   Aby dodać ogólne dni buforowe do indywidualnych dni buforowych, w polu **ogólne dni buforowe** wprowadź liczbę dni od dnia, kiedy odbiorca wysyła płatności do dnia, kiedy organizacja otrzymuje płatności.

Ustaw indywidualne dni buforowe w umowie dotyczącej projektu. Dni są obliczane na podstawie daty płatności faktury sprzedaży dotychczasowych doświadczeń firmy ze schematem płatności odbiorcy.

#### <a name="actual-cash-inflow"></a>Rzeczywiste przychody gotówkowe

Rzeczywiste przepływy pieniężne są podobne do przepływów prognozowanych, umożliwiają jednak rozpoczęcie obliczeń od pierwszej daty faktury. Oto przykład:

-   **Data faktury:** 2 marca 2012.
-   **Data wykonania:** 16 marca 2012 r. Warunki płatności są ustawione na 14 dni.
-   **Data oczekiwanej płatności za sprzedaż:** 29 marca 2012 r. Obliczenie obejmuje trzy ogólne dni buforowe i 10 indywidualnych dni buforowych.

#### <a name="cost-forecasting"></a>Prognozowanie kosztów

Na podstawie zdefiniowanych dni data płatności kosztu może się różnić od daty projektu. W takim przypadku data płatności kosztu jest obliczana przez dodanie liczby dni od daty projektu do liczby dni w polu warunki płatności. 

Na przykład data projektu dla transakcji to 5 marca 2012 i są ustawione następujące warunki płatności:

-   **Godziny:** Bieżący miesiąc (**M**)
-   **Wydatki:** 14 dni (**D14**)
-   **Towary:** 30 dni (**D30**)

Na podstawie tych ustawień poniżej znajdują się daty płatności kosztu dla każdego typu transakcji:

-   **Liczba godzin:** 31 marca 2012; ostatni dzień wybranego miesiąca.
-   **Wydatki:** 19 marca 2012; 14 dni po dacie transakcji.
-   **Pozycje:** 4 kwietnia 2012; 30 dni po dacie transakcji.

> [!NOTE] 
> Data wykonania dla zamówienia zakupu jest ustalona na podstawie transakcji dostawcy po utworzeniu zamówienia zakupu dla projektu. Termin nie jest określany przez żadne ustawienia domyślne. 

Data płatności kosztu nie jest obliczana na dni buforowe. Po zakończeniu projektu wszystkie operacje obliczania kosztów i fakturowania zostają ukończone, a kwoty kosztów i sprzedaży zostają zaksięgowane na kontach zysków i strat. 

Po zakończeniu wszystkich sprzedaży i faktur dostawcy można wyświetlić relację między polami na stronach **przepływów pieniężnych** i **Zestawienia projektu**.

| Strona Przepływy pieniężne | Strona Zestawienia projektu |
|----------------|-------------------------|
| Przychody gotówkowe   | Przychód                 |
| Rozchody gotówkowe  | Łączny koszt              |
| Przychody gotówkowe netto | Marża brutto            |

### <a name="review-costs"></a>Przegląd kosztów

Istnieje możliwość monitorowania kosztów ponoszonych przez organizację w czasie trwania projektu na stronie **Kontrola kosztów**. Przez porównanie pierwotnie zaplanowane koszty projektu z bieżącymi kosztami rzeczywistymi i kosztami ustalonymi można określić, czy projekt mieści się w budżecie, przekracza budżet lub jego koszty są mniejsze niż przewidywane. 

> [!NOTE] 
> Korzystając ze strony **Kontrola kosztów** do sprawdzenia bieżącego kosztu projektu, użyj modeli prognozy wybranych dla pierwotnego i pozostałego budżetu. Jeśli podczas obliczania kosztów wybierzesz inne modele prognozy, wyniki obliczeń nie będą prawidłowe.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Wyświetlanie pozostałych zaplanowanych kosztów

Jeśli wybierzesz **Pozostały budżet** jako metodę kontroli kosztów na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**, strona **Kontrola kosztów** obliczy koszty, które jeszcze nie zostały zaksięgowane jako rzeczywiste ani oznaczone jako ustalone. W szczególności kwoty na karcie **Ogólne** w dolnym okienku strony **Kontrola kosztów** są obliczane w następujący sposób:

-   **Koszt rzeczywisty** — całkowitą kwotę, która została wydana w projekcie dla wybranego wiersza kosztu. Kwota kosztu rzeczywistego jest obliczana na stronie **aktualizacje księgi**.
-   **Ustalony koszt** — dodatkowa kwota wydatków, które firma zobowiązała się zapłacić. Kwoty kosztu ustalonego są obliczane na stronie **Koszt ustalony**.
-   **Pozostały budżet** — kwota oryginalnej kwoty budżetu, która jest nadal dostępna dla wybranego wiersza kosztu. Pozostała kwota budżetu jest obliczana na stronie **podglądu księgi głównej**.
-   **Łączny koszt** – suma kosztów rzeczywistych, ustalonych i pozostałych.

Na stronie **Kontrola kosztów**, na karcie **Odchylenia**, możesz przejrzeć porównanie kosztów łącznych z pierwotnym budżetem. Porównanie to zawiera wszelkie różnice między tymi kwotami. Dzięki temu można sprawdzić, które dane nie są zgodne. Wartości odchyleń są obliczane następująco:

-   **Budżet pierwotny** — kwota, która została pierwotnie uwzględniona w budżecie dla wybranego wiersza kosztu. Kwota pierwotnego budżetu jest obliczana na stronie **podglądu księgi głównej**.
-   **Łączny koszt**– suma kosztów rzeczywistych, ustalonych i pozostałych określonych na karcie **Ogólne**.
-   **Odchylenie** — różnica między kosztem łącznym a pierwotną wysokością budżetu.
-   **Odchylenie na podstawie ilości** — łączna różnica w kwocie między prognozą pierwotną i prognozą całkowitą. Ta różnica może być wyrażona matematycznie jako [(całkowita prognozowana ilość) * (pierwotna średnia cena - całkowita średnia cena)] To obliczenie dotyczy tylko godzin w projekcie.
-   **Odchylenie na podstawie ceny** — łączna różnica w kwocie między prognozą pierwotną i prognozą całkowitą. Ta różnica może być wyrażona matematycznie jako [(pierwotna prognozowana cena) * (pierwotna prognozowana ilość - całkowita prognozowana ilość)]. To obliczenie dotyczy tylko godzin w projekcie.

#### <a name="viewing-the-total-budgeted-amounts"></a>Wyświetlanie łącznych zaplanowanych kosztów

Jeśli jako metodę kontroli kosztów wybrano **łączny budżet** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**, strona **Kontrola kosztów** obliczy koszty rzeczywiste i łączne koszty projektu, ułatwiając wykrywanie wszelkich różnic między tymi kosztami. W szczególności kwoty na stronie **Kontrola kosztów** w kolumnach w okienku na dole karty **Ogólne** są obliczane w następujący sposób:

-   **Łączny koszt w budżecie** — sumy budżetu dla wybranego wiersza kosztu.
-   **Koszt rzeczywisty** — całkowita kwota kosztów, która została wydana w projekcie do określonego dnia dla wybranych wierszy kosztu.
-   **Koszt ustalony** — całkowita kwota, która została ustalona w projekcie dla wybranego wiersza kosztu.
-   **Odchylenie** — różnica między sumą kosztów rzeczywistych i ustalonych a łącznym kosztem. Odchylenie pokazuje, czy należy określić dodatkowe koszty dla łącznego budżetu.

Na stronie **Kontrola kosztów**, na karcie **odchylenia**, możesz przejrzeć różnice między łącznym budżetem i pierwotnym budżetem na podstawie informacji w następujących polach:

-   **Budżet pierwotny** — kwota, która została pierwotnie uwzględniona w budżecie dla wybranego wiersza kosztu. Kwota pierwotnego budżetu jest obliczana na stronie **podglądu księgi głównej**.
-   **Łączny koszt w budżecie** — łączny koszt, który został pierwotnie uwzględniony w budżecie dla wybranego wiersza kosztu. Kwota łącznego kosztu w budżecie jest obliczana na stronie **podglądu księgi głównej**.
-   **Odchylenie** — odchylenie dla wiersza kosztu. Kwota ta jest obliczana przez odjęcie od kosztów zaplanowanych w pierwotnym budżecie łącznych kosztów.
-   **Odchylenie na podstawie ilości** — łączna różnica w kwocie między budżetem pierwotnym i budżetem całkowitym. Wartość ta została obliczona przez odjęcie od liczby godzin zaplanowanych w pierwotnym budżecie łącznej liczby godzin, a następnie pomnożenie powstałej różnicy przez zaplanowany w pierwotnym budżecie koszt własny. Różnica ta może być wyrażona matematycznie jako (zaplanowany w pierwotnym budżecie koszt własny) x (godziny w pierwotnym budżecie — łączna liczba godzin). To obliczenie dotyczy tylko godzin w projekcie.
-   **Odchylenie na podstawie ceny** – Wartość ta została obliczona przez odjęcie od liczby godzin zaplanowanych w pierwotnym budżecie łącznej liczby godzin, a następnie pomnożenie powstałej różnicy przez łączną liczbę zużytych godzin. Różnica ta może być wyrażona matematycznie jako (wszystkie godziny wykorzystane w projekcie) x (godziny w pierwotnym budżecie — łączna liczba godzin). To obliczenie dotyczy tylko godzin w projekcie.

### <a name="analyze-utilization"></a>Analiza wykorzystania

Stawka wykorzystania jest wartością procentową czasu, w którym pracownik wykonuje płatną lub produktywną pracę w danym okresie pracy. Godziny do zafakturowania są godzinami pracy pracownika, za które można naliczyć opłatę określonemu odbiorcy. 

Stawka wykorzystania pracownika obliczana jest poprzez podzielenie liczby godzin do zafakturowania przez liczbę godzin pracy w danym okresie. Na przykład jeśli pracownik ma 30 godzin do zafakturowania w okresie, a liczba godzin pracy w tym samym okresie wynosi 40, stawka wykorzystania pracownika wynosi 75 procent. 

Podczas obliczania wykorzystania pracownika można obliczyć albo stawkę podlegającą rozliczeniu, albo stawkę wydajności.

-   **Stawka rozliczana** — różnica między liczbą godzin do zafakturowania i godzin nie do zafakturowania lub normą godzinową.
-   **Stawka wydajności** — różnica między liczbą godzin płatnych i niepłatnych lub normą godzinową. Godziny płatne są to godziny, które pracownik przeznacza na pracę na rzecz określonego projektu. Godziny płatne są zwykle naliczane odbiorcom, chyba że dotyczą projektów wewnętrznych. Godziny niepłatne to godziny, za które nigdy nie nalicza się opłat odbiorcom.

Stawki wykorzystania oblicza się na stronie **Wykorzystanie godzin**. Obliczenia są oparte na domyślnych preferencjach. Te preferencje określają też sposób liczenia godzin poprzez przypisanie **wykorzystania** lub **obciążenia** dla każdego z typu projektu. Dotyczy to obliczeń stawek do zafakturowania i obliczania stawki wydajności.

-   **Wykorzystanie** — godziny zgłoszone dla określonego typu projektu są zawsze uwzględniane do zafakturowania lub wykorzystania wydajności.
-   **Obciążenie** — godziny zgłoszone dla określonego typu projektu są zawsze uwzględniane jako niepodlegające fakturowaniu lub wykorzystaniu wydajności.
-   **Według właściwości wiersza** — właściwości wiersza określonej transakcji godzinowej określają, czy godziny będą przydzielane do zafakturowania lub wykorzystania wydajności.
-   **Nieuwzględnione** — godziny nie są uwzględniane w obliczeniach do zafakturowania lub wykorzystania wydajności.

Na stronie **wykorzystanie godzin** poza ogólną procentową stawką wykorzystania dla pracownika lub projektu można wyświetlić liczbę godzin, które były używane do obliczania stawki wykorzystania dla każdego z następujących typów godzin:

-   **Godziny nieuwzględnione** — te godziny nie są uwzględniane w obliczeniach stawki wykorzystania godzin.
-   **Godziny uwzględnione** — te godziny są obliczane przez dodanie godzin wykorzystania i godzin obciążenia. Te godziny są uwzględniane w obliczeniach stawki wykorzystania.
-   **Godziny obciążenia** — w przypadku obliczania stawki rozliczania te godziny są takie same jak godziny niepłatne. W przypadku obliczania stawki wydajności te godziny są takie same jak godziny niepłatne.
-   **Godziny obciążenia** — w przypadku obliczania stawki rozliczania te godziny są takie same jak godziny niepłatne. W przypadku obliczania stawki wydajności te godziny są takie same jak godziny niepłatne.

Podczas obliczania stawki wykorzystania dla pracownika, można użyć norm godzinowych lub godzin uwzględnionych. Jeśli używasz godzin uwzględnionych, upewnij się, że pracownicy rejestrują cały swój czas pracy w danym okresie, ponieważ wynikiem obliczenia jest wartość procentowa wprowadzonych godzin. Podczas obliczania stawki wykorzystania godzin dla projektu, umowy dotyczącej projektu, rekordu odbiorcy lub kategorii, do obliczeń należy użyć godzin uwzględnionych.

### <a name="review-project-statements"></a>Przegląd zestawień projektu

Można utworzyć zestawienie projektu, aby wyświetlić szybki podgląd postępu projektu. Po uruchomieniu zestawienia projektu można określić kryteria, które są używane do obliczania zestawienia, dokonując wyborów na karcie **ogólne** na stronie **zestawienia projektu**. Można wybrać uwzględnienie lub wykluczenie następujących informacji:

-   Typy projektów
-   Typy transakcji
-   Data projektu/data księgi
-   Dane

Po obliczeniu zestawienia możesz wyświetlić następujące informacje na różnych kartach strony **Zestawienie projektu**:

-   **Ogólne** — ogólne informacje dotyczące podstawowej struktury zysków i strat projektu.
-   **Zyski i straty** — informacje o przychodach przyszłych okresów.
-   **PWT** — informacje o saldach konta PWT.
-   **Zużycie** — informacje na temat zużycia godzin, wydatków, towarów i transakcji listy płac.
-   **Faktury** — informacje dotyczące faktury i fakturowania akonto.
-   **Stawka godzinowa** — stawki godzinowe dla godzin zaksięgowanych na kontach przychodów i kosztów.





