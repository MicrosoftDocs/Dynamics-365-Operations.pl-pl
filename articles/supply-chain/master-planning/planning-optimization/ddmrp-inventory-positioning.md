---
title: Lokalizacja zapasów
description: Ten artykuł zawiera informacje na temat strategicznego pozycjonowania zapasów, które polega na identyfikacji punktów rozłącznych w łańcuchu dostaw, w których można gromadzić zapasy pod ręką, aby skrócić czas realizacji zamówień i zniwelować wstrząsy w łańcuchu dostaw.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 847108575cbf7207282db00d731363c8cfad883a
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689546"
---
# <a name="inventory-positioning"></a>Lokalizacja zapasów

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Strategiczne pozycjonowanie zapasów polega na identyfikacji punktów rozłącznych w łańcuchu dostaw, w których można gromadzić zapasy. Takie podejście jest stosowane głównie po to, by skrócić czas realizacji zamówień i zniwelować wstrząsy w łańcuchu dostaw. Pozwala to na złagodzenie "efektu byka", ponieważ zmienność popytu nie jest przekazywana w dół łańcucha dostaw. (*Efekt bicza* oznacza, że małe wahania popytu na poziomie detalicznym mogą powodować stopniowo większe wahania popytu na poziomie hurtowni, dystrybutorów, producentów i dostawców surowców).

Pozycjonowanie zapasów to pierwszy etap Planowania zasobów materiałowych kierowanych popytem (DDMRP).

## <a name="inventory-positioning-for-manufacturing"></a>Pozycjonowanie zapasów w produkcji

W tej części przedstawiono przykład, który pokazuje, jak podejmować decyzje dotyczące pozycjonowania zapasów w przypadku produkcji typowej poduszki. Poduszka ma wielopoziomową listę materiałów (BOM), jak pokazano na poniższej ilustracji.

![Przykładowy wielopoziomowy wykaz materiałów (BOM) dla poduszki.](media/ddmrp-bom-example.png "Przykładowy wielopoziomowy wykaz materiałów (BOM) dla poduszki")

### <a name="choose-your-decoupling-points"></a>Wybierz punkty odsprzęgania

Kiedy wybierasz, gdzie umieścić punkty odłączenia, weź pod uwagę wszystkie poniższe aspekty każdego elementu w BOM jako kryteria:

- Zmienność zewnętrzna
- Dźwignia i elastyczność zapasów
- Ochrona operacji krytycznych
- Czas tolerancji klienta
- Horyzont widoczności zamówień sprzedaży
- Potencjał rynku czas realizacji

W przykładzie z poduszką możesz umieścić pierwszy punkt odłączenia na *kostkach piankowych* z następujących powodów:

- Trudno jest zdobyć materiały używane do produkcji kostek pianki, a ich dostępność jest zmienna. Dlatego kryterium *zewnętrznej zmienności* jest spełnione.
- Kostki pianki mogą być cięte na wiele różnych kształtów i rozmiarów, aby stworzyć wkłady z pianki do innych produktów, które produkujesz, oprócz poduszki. Dlatego kryterium *dźwigni i elastyczności zapasów* jest spełnione.

Następny punkt odłączenia możesz umieścić w *zestawie tkanin*, czyli wstępnie wyciętej tkaninie na poduszki. Możesz wybrać ten punkt, ponieważ masz tylko jedną maszynę do cięcia tkanin. Dlatego kryterium *ochrony przed krytycznym działaniem* jest spełnione.

Ostatni punkt rozłączenia możesz umieścić na gotowym elemencie poduszki. Możesz wybrać ten punkt, ponieważ masz bardzo niski *czas tolerancji klienta* na sprzedaż oraz ponieważ twój *horyzont widoczności zamówienia sprzedaży* jest dość krótki. Dlatego chcesz mieć pewność, że posiadasz zapasy, które pozwolą Ci zrealizować przychodzące zamówienia. Możesz również ustalić wyższą cenę, utrzymując tak krótki czas realizacji, do czego odnosi się kryterium *rynkowego potencjału czasu realizacji*.

Na podstawie tej analizy na poniższej ilustracji pokazano, jak będzie wyglądać BOM poduszki. Żółte symbole inwentarza podkreślają punkty odłączenia.

![Przykładowy BOM z zaznaczonymi punktami odsprzęgania.](media/ddmrp-bom-decoupling-example.png "Przykładowy BOM z zaznaczonymi punktami odsprzęgania")

### <a name="calculate-your-decoupled-lead-time"></a>Obliczenie odłączonego czasu realizacji

W tej części pokazano, jak obliczyć nowe czasy realizacji po wprowadzeniu punktów rozłącznych.

Na poniższej ilustracji dla przykładu poduszki, który został przedstawiony w poprzednim rozdziale, czasy realizacji są pokazane w szarych polach w lewym górnym rogu każdego elementu BOM. Pola z czerwonym obrysem oznaczają pozycje, które wpływają na łączny czas realizacji (suma najdłuższych czasów realizacji na każdym poziomie BOM). Czas realizacji wynosi 21 dni, gdy zaczynasz od zera.

![Przykład BOM z czasami realizacji.](media/ddmrp-bom-lead-times-example.png "Przykład BOM z czasami realizacji")

Jeśli jednak zastosujesz punkty rozłączenia, które wcześniej wybrałeś, przedmioty rozłączone będą zawsze w magazynie. Dlatego ich czas realizacji będzie wynosił 0 (zero). Nowy czas realizacji zamówienia na poduszkę wynosi teraz tylko pięć dni: dwa dni na zakup nici i trzy dni na wyprodukowanie poduszki. Ten czas realizacji nazywany jest *odłączonym czasem realizacji*.

![Przykład odłączonego czasu realizacji.](media/ddmrp-bom-decoupled-lead-time-example.png "Przykład odłączonego czasu realizacji")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Strategiczne pozycjonowanie zapasów w modelu detalicznym

Ponieważ detaliści przechowują tylko gotowe produkty, listy BOM nie stanowią problemu. Jednak sprzedawcy mogą nadal korzystać z DDMRP, ustalając strategiczne pozycje zapasów i poziomy buforów na podstawie miejsc składowania w sieci dystrybucji.

Poniższa ilustracja przedstawia przykład firmy, która ma centrum dystrybucyjne w Seattle oraz sklepy w Bostonie, Atlancie i Portland.

![Odłączanie punktów na podstawie lokalizacji w modelu detalicznym.](media/ddmrp-retail-decoupl-points-example.png "Odłączanie punktów na podstawie lokalizacji w modelu detalicznym")

Możesz zdecydować, że czas przenoszenia produktu w postaci koca między centrum dystrybucyjnym a sklepami narusza Twoją *tolerancję klienta*, ponieważ Twoi klienci oczekują, że koc będzie dostępny w magazynie w momencie wizyty. W tym przypadku utworzysz w każdym z trzech sklepów punkt rozłączny dla przedmiotu w postaci koca. Każdy sklep będzie miał różne poziomy buforów, zależnie od czasu realizacji zamówienia, wzorców popytu itp.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Implementowanie pozycjonowania zapasów w Dynamics 365 Supply Chain Management

W tym rozdziale opisano, jak zaimplementować strategię pozycjonowania zapasów w programie Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Utwórz grupy pokrycia elementów, które tworzą punkty rozłączne

Pozycje stają się punktami rozłącznymi, gdy należą do grupy pokrycia, która jest skonfigurowana z **Kodem zapotrzebowania** wartości *Punkt odłączenia*. Dlatego pierwszym krokiem w procesie tworzenia DDMRP jest decyzja, które grupy pokrycia należy wdrożyć w strategii DDMRP, a następnie utworzyć je, wykonując poniższe kroki.

1. Przejdź do menu **Planowanie główne \> Konfiguracja \> Zapotrzebowanie \> Grupy zapotrzebowania**.
1. W okienku akcji wybierz opcję **Nowe**, aby utworzyć grupę zapotrzebowania.
1. Wprowadź informacje identyfikujące grupę objętą ubezpieczeniem, a następnie wybierz kalendarz, którego chcesz użyć.
1. Na zakładce **Ogólne** ustaw pole **Kod pokrycia** na *Punkt odłączenia*. To ustawienie spowoduje, że wszystkie elementy należące do tej grupy pokrycia będą traktowane jako punkty rozłączne dla DDMRP. Włącza również wszystkie ustawienia DDMRP dla tej grupy, co zostało opisane w dalszej części procedury.
1. Na zakładce **Inne**, w sekcji **Parametry DDMRP**, ustaw następujące pola:

    - **Współczynnik czasu realizacji** - Określ współczynnik (jako wartość dziesiętną pomiędzy 0 a 1), aby kontrolować wpływ czasu realizacji na obliczanie minimalnego i maksymalnego poziomu zapasów dla pozycji w tej grupie pokrycia. Ogólnie rzecz biorąc, im dłuższy jest czas realizacji zamówienia, tym niższy powinien być jego współczynnik czasu realizacji. Niższy współczynnik czasu realizacji powoduje niższy minimalny i maksymalny poziom zapasów, a więc mniejsze i częstsze zamówienia. Metodologia DDMRP zaleca wartość pomiędzy 0,20 a 0,40 dla przedmiotów o długim czasie realizacji, pomiędzy 0,41 a 0,60 dla przedmiotów o średnim czasie realizacji oraz pomiędzy 0,61 a 1,00 dla przedmiotów o krótkim czasie realizacji. Aby uzyskać więcej informacji, zobacz [Profil i poziomy buforów](ddmrp-buffer-profile-and-levels.md).
    - **Współczynnik zmienności** - Określ współczynnik (jako wartość dziesiętną z przedziału od 0 do 1), aby kontrolować wpływ zmiennego popytu na obliczanie minimalnego poziomu zapasów dla artykułów w tej grupie pokrycia. Ogólnie rzecz biorąc, im bardziej zmienny jest popyt na daną rzecz, tym wyższy powinien być jej współczynnik zmienności. Wyższy współczynnik zmienności powoduje wyższy minimalny poziom zapasów. Metodologia DDMRP zaleca wartość pomiędzy 0,00 a 0,40 dla przedmiotów o małej zmienności, pomiędzy 0,41 a 0,60 dla przedmiotów o średniej zmienności oraz pomiędzy 0,61 a 1,00 dla przedmiotów o dużej zmienności. Aby uzyskać więcej informacji, zobacz [Profil i poziomy buforów](ddmrp-buffer-profile-and-levels.md).
    - **Minimalny, maksymalny i okres ponownego zamawiania** - Określ, jak często mają być obliczane wartości bufora (*dziennie* lub *tygodniowo*).

1. Na zakładce **Inne**, w sekcji **Średnie dzienne użycie**, ustaw następujące pola:

    - **Średnie dzienne zużycie** - Wybierz, na jakich okresach czasu ma być oparte obliczanie średniego dziennego zużycia (ADU). Należy wybrać jedną z następujących opcji:

        - *Przeszłość* - Zobacz tylko przeszłe użycie dla liczby dni określonej w polu **Przeszły okres (dni)**. ADU oblicza się jako całkowite zapotrzebowanie na daną pozycję w okresie obliczeniowym (w jednostkach magazynowych) podzielone przez liczbę dni w okresie obliczeniowym.
        - *Naprzód* - Patrz tylko na przewidywane przyszłe użycie (w tym prognozy) przez liczbę dni określoną w polu **Okres naprzód (dni)**. ADU oblicza się jako całkowite zapotrzebowanie na daną pozycję w okresie obliczeniowym (w jednostkach magazynowych) podzielone przez liczbę dni w okresie obliczeniowym. 
        - *Mieszane* - Patrz zarówno na przeszłe, jak i przyszłe użycie. Obowiązują ustawienia dla pola **Ostatni okres (dni)**, pola **Przyszły okres (dni)** oraz opcje mieszania. 

            *Mieszane ADU* = (\[*ważenie przeszłe* × *przeszłe ADU*\] + \[*ważenie wyprzedzające* × *wyprzedzające ADU*\]) ÷ (*ważenie przeszłe* + *ważenie wyprzedzające*)

    - **Okres przeszły (dni)** - wpisz liczbę dni przeszłych (do dnia dzisiejszego włącznie), które system powinien uwzględnić przy obliczaniu ADU przedmiotów z tej grupy pokrycia. To ustawienie ma zastosowanie tylko wtedy, gdy pole **Średnie dzienne użycie na podstawie** jest ustawione na *Przeszłość* lub *Mieszane*.
    - **Okres przyszły (dni)** - wpisz liczbę przyszłych dni (od dzisiaj do określonego dnia), które system powinien uwzględnić przy obliczaniu ADU przedmiotów w tej grupie pokrycia. To ustawienie ma zastosowanie tylko wtedy, gdy pole **Średnie dzienne użycie na podstawie** jest ustawione na *Przyszłość* lub *Mieszane*.
    - **Względna waga minionego okresu dla mieszanego średniego dziennego zużycia** - wpisz wagę (w procentach), która ma być zastosowana do minionego okresu przy obliczaniu mieszanego ADU. To ustawienie ma zastosowanie tylko wtedy, gdy pole **Średnie dzienne użycie na podstawie** jest ustawione na *Mieszane*.
    - **Względna waga okresu wyprzedzającego dla mieszanego średniego dziennego zużycia** - wpisz wagę (w procentach), która ma być zastosowana do okresu wyprzedzającego przy obliczaniu mieszanego ADU. To ustawienie ma zastosowanie tylko wtedy, gdy pole **Średnie dzienne użycie na podstawie** jest ustawione na *Mieszane*.

1. W przypadku wszystkich pozostałych zakładek i pól wprowadź szczegółowe ustawienia, które są używane do obliczania wymagań dla pozycji powiązanych z daną grupą pokrycia.

### <a name="set-an-item-as-a-decoupling-point"></a>Ustaw element jako punkt rozłączenia

Aby ustawić element jako punkt rozłączenia, wykonaj następujące kroki.

1. Przejdź do **Zarządzanie informacjami o produktach\> Produkty \> Zwolnione produkty**.
1. Znajdź i wybierz zwolniony element, który chcesz skonfigurować dla DDMRP.
1. W okienku akcji otwórz kartę **Plan** i wybierz pozycję **Objęcie przedmiotu**.
1. Na stronie **Zapotrzebowanie na towar** może być już wymienionych kilka rekordów pokrycia artykułu, z których każdy dotyczy innej kombinacji wymiarów magazynu i produktu. Możesz wybrać istniejący rekord pokrycia elementu, który dotyczy wymiarów, dla których chcesz utworzyć punkt rozłączenia. Możesz też wybrać **Nowy** na panelu akcji, aby utworzyć nowy rekord zapotrzebowania na towar.
1. Skonfiguruj rekord pokrycia przedmiotu w zwykły sposób. Musisz przynajmniej określić miejsce i magazyn, w którym będzie obowiązywał punkt rozłączenia.
1. Gdy odpowiedni rekord jest nadal zaznaczony, wybierz zakładkę **Ogólne**.
1. Zaznacz pole wyboru **Użyj specyficznych ustawień**.
1. W polu **Grupa zapotrzebowania** należy ustawić grupę zapotrzebowania, która jest ustawiona w celu tworzenia punktów dekompensowania (zgodnie z opisem w poprzedniej sekcji).
1. Element jest teraz skonfigurowany jako punkt odłączenia. Zazwyczaj, kiedy używasz DDMRP, konfigurujesz tutaj również ustawienia, które wpływają na wielkość buforów i ilość zamawianych produktów. Możesz jednak dokończyć tę konfigurację później. Więcej informacji znajdziesz w rozdziale [Ustawianie buforów dla punktu rozłącznego.](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Aby zaplanować pozycje, które nie są punktami rozłącznymi, wykonaj te same kroki, które stosujesz w przypadku standardowego planowania zapotrzebowania materiałowego (MRP).
