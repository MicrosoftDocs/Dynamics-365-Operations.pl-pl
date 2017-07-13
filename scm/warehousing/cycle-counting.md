---
title: "Inwentaryzacja ciągła"
description: "W tym artykule opisano sposób używania inwentaryzacji ciągłej w aplikacji magazynowej dostępnej w module zarządzania magazynem. Artykuł nie ma zastosowania do aplikacji magazynowej zawartej w module zarządzania zapasami."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 50671
ms.assetid: 49f5c431-b043-4170-aa24-b7d5d1ee063e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: ebc7789d7b0be5db4a0faf4309bc3640f51956c6
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# Inwentaryzacja ciągła
<a id="cycle-counting" class="xliff"></a>

[!include[banner](../includes/banner.md)]


W tym artykule opisano sposób używania inwentaryzacji ciągłej w aplikacji magazynowej dostępnej w module zarządzania magazynem. Artykuł nie ma zastosowania do aplikacji magazynowej zawartej w module zarządzania zapasami.

Inwentaryzacja cykliczna jest procesem magazynowym, który służy do inspekcji pozycji magazynowych. Proces inwentaryzacji ciągłej można opisać w trzech krokach:

1.  **Tworzenie inwentaryzacji ciągłej** — Praca inwentaryzacji ciągłej może być tworzona automatycznie na podstawie parametrów progu dla towarów lub za pomocą planu inwentaryzacji ciągłej. Alternatywnie można ręcznie utworzyć pracę inwentaryzacji ciągłej za pomocą parametrów towaru lub magazynu na stronie **Praca inwentaryzacji ciągłej wg pozycji** lub stronie **Praca inwentaryzacji ciągłej wg lokalizacji**.
2.  **Przetwarzaj inwentaryzację ciągłą** — Po utworzeniu pracy inwentaryzacji ciągłej można wykonać tę pracę, zliczając towary w lokalizacji w magazynie, a następnie za pomocą urządzenia przenośnego wprowadzając wynik w programie Microsoft Dynamics 365 for Finance and Operations. Ewentualnie można zliczyć towary w jednej lokalizacji bez tworzenia inwentaryzacji ciągłej. Ten proces jest określany jako *inwentaryzacja ciągła punktowa*.
3.  **Uzgadnianie różnic w policzonej wartości** — Po wykonaniu inwentaryzacji cyklicznej wszystkie towary, dla których istnieją różnice w zliczonej wartości, będą miały stan pracy **Oczekiwanie na przegląd** na stronie **Cała praca**. Różnice te można uzgodnić na stronie **Praca inwentaryzacji ciągłej oczekuje na przegląd**.

Poniższa ilustracja pokazuje proces inwentaryzacji ciągłej. ![Przebieg procesu w przypadku inwentaryzacji ciągłej](./media/performcyclecountinginawarehouselocation.jpg)

## Warunki wstępne inwentaryzacji ciągłej
<a id="cycle-counting-prerequisites" class="xliff"></a>
W poniższej tabeli przedstawiono warunki wstępne, które muszą być spełnione przez rozpoczęciem inwentaryzacji ciągłej.
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
<td>Pozycja</td>
<td>Dla danego towaru musi być możliwa obsługa zarządzania magazynem.</td>
</tr>
<tr class="even">
<td>Magazyn</td>
<td>Musi być możliwe zarządzanie danym magazynem. Aby włączyć magazyn dla procesów zarządzania magazynem, na stronie <strong>Magazyny</strong> wybierz magazyn, a następnie zaznacz opcję <strong>Użyj procesów zarządzania magazynami</strong>. Aby umożliwić pracownikom przemieszczanie palet podczas inwentaryzacji ciągłej, na skróconej karcie <strong>Zarządzanie magazynem</strong> zaznacz opcję <strong>Zezwalaj na przenoszenie palety podczas inwentaryzacji ciągłej</strong>.</td>
</tr>
<tr class="odd">
<td>Pula pracy</td>
<td>Opcjonalnie: Utwórz pulę pracy, aby segregować pracę magazynową na podstawie typu pracy (w tym przypadku pracy inwentaryzacji ciągłej).</td>
</tr>
<tr class="even">
<td>Lokalizacje</td>
<td>Włącz inwentaryzację ciągłą dla lokalizacji. Aby umożliwić inwentaryzację ciągłą w lokalizacji w magazynie, na stronie <strong>Profile lokalizacji</strong> zaznacz opcję <strong>Pozwól na inwentaryzację ciągłą</strong>.</td>
</tr>
<tr class="odd">
<td>Parametry zarządzania magazynem</td>
<td>Ustaw parametry inwentaryzacji ciągłej. Na stronie <strong>Parametry zarządzania magazynem</strong> określ domyślny kod typu korekty, identyfikator klasy pracy oraz priorytet pracy inwentaryzacji ciągłej.</td>
</tr>
<tr class="even">
<td>Urządzenie przenośne</td>
<td><ul>
<li>Na stronie <strong>Elementy menu urządzenia przenośnego</strong> utwórz element menu dla jednej z następujących metod:
<ul>
<li>Inwentaryzacja ciągła sterowana przez użytkownika</li>
<li>Inwentaryzacja ciągła sterowana przez system</li>
<li>Grupowanie inwentaryzacji ciągłej</li>
<li>Inwentaryzacja ciągła punktowa</li>
</ul>
</li>
<li>Skonfiguruj menu dla urządzenia przenośnego.</li>
<li>Utwórz konto użytkownika pracy i przypisz menu urządzenia przenośnego do identyfikatora użytkownika pracy.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Pokrewne zadanie konfiguracji</td>
<td>Skonfiguruj planu inwentaryzacji ciągłej dla lokalizacji inwentaryzacji.</td>
</tr>
</tbody>
</table>

## Automatyczne tworzenie pracy inwentaryzacji ciągłej
<a id="automatically-create-cycle-counting-work" class="xliff"></a>
Istnieją dwa sposoby planowania cyklicznego tworzenia pracy inwentaryzacji ciągłej: skonfigurowanie progów inwentaryzacji ciągłej lub skonfigurowanie planów inwentaryzacji ciągłej.

-   Próg inwentaryzacji ciągłej wskazuje limit ilościowy lub procentowy dla pozycji magazynowych. Po przekroczeniu limitu progu, praca inwentaryzacji ciągłej jest tworzona automatycznie.
-   Plan inwentaryzacji ciągłej powoduje natychmiastowe lub okresowe tworzenie pracy inwentaryzacji ciągłej za pomocą zadania wsadowego. Po utworzeniu pracy inwentaryzacji ciągłej wiersz tej pracy zawiera informacje o lokalizacji, która ma być inwentaryzowana. Dostępne zapasy skojarzone z tą lokalizacją nie są zablokowane, w związku z czym są dostępne na potrzeby rezerwacji i przetwarzania dostaw wychodzących, nawet jeśli istnieje otwarta praca inwentaryzacji.

### Tworzenie pracy inwentaryzacji ciągłej na podstawie parametrów progu dla towarów
<a id="create-cycle-counting-work-based-on-threshold-parameters-for-items" class="xliff"></a>

Pracę inwentaryzacji ciągłej można utworzyć, gdy ilość towaru w lokalizacji spadnie poniżej określonej wartości progowej. Na przykład w lokalizacji istnieje 60 sztuk towaru, dla którego próg inwentaryzacji ciągłej wynosi 40. Podczas transakcji zamówienia sprzedaży 25 sztuk jest pobieranych z lokalizacji i umieszczanych w lokalizacji pośredniej. Ponieważ nowa liczba sztuk (35) jest mniejsza niż ilość w progu, inwentaryzacja ciągła jest tworzona automatycznie dla lokalizacji.

### Tworzenie planu inwentaryzacji ciągłej
<a id="schedule-cycle-counting-work" class="xliff"></a>

Plany inwentaryzacji ciągłej umożliwiają natychmiastowe lub okresowe tworzenie pracy inwentaryzacji ciągłej. Konfigurując plany inwentaryzacji ciągłej, można kontrolować pulę pracy, dla której jest tworzona praca inwentaryzacji ciągłej, maksymalną liczbę prac inwentaryzacji tworzoną dla towarów w różnych lokalizacjach oraz liczbę dni do ponownej inwentaryzacji lokalizacji w magazynie. Na przykład towar jest dostępny w trzech lokalizacjach w magazynie, a ustawiono maksymalną liczbę cykli inwentaryzacji na **2**. W tym przypadku po uruchomieniu planu inwentaryzacji ciągłej zostaną utworzone dwie prace inwentaryzacji dla dwóch lokalizacji, w których znajduje się towar. Inny przykład: Ustawiasz liczbę dni między sesjami inwentaryzacji na **5**. W takim przypadku praca inwentaryzacji ciągłej jest tworzona co pięć dni. Jednak jeśli praca inwentaryzacji ciągłej zostanie wykonana w 3. dniu, następna praca inwentaryzacji ciągłej zostanie utworzona po 5 dniach od ostatniego wykonania pracy inwentaryzacji ciągłej, czyli w 8. dniu.

## Ręczne tworzenie inwentaryzacji ciągłej
<a id="create-cycle-counting-work-manually" class="xliff"></a>
Aby ręcznie utworzyć pracę inwentaryzacji ciągłej, można użyć strony **Praca inwentaryzacji ciągłej wg pozycji** lub **Praca inwentaryzacji ciągłej wg lokalizacji**. Można określić maksymalną liczbę prac inwentaryzacji ciągłej, jaka ma zostać utworzona. Na przykład jeśli kierownik magazynu określa wartość równą **5**, praca inwentaryzacji ciągłej jest tworzona dla pięciu lokalizacji, nawet jeśli towar znajduje się w 10 lokalizacjach. Można również wybrać identyfikator puli pracy, któremu zostaną przypisane identyfikatory tworzonych prac inwentaryzacji ciągłej. Gdy identyfikator puli pracy jest przetwarzany dla inwentaryzacji ciągłej, identyfikatory inwentaryzacji ciągłej przypisane do puli pracy są przetwarzane jako grupa.

## Wykonywanie inwentaryzacji ciągłej za pomocą urządzenia przenośnego
<a id="perform-a-cycle-count-by-using-a-mobile-device" class="xliff"></a>
Istnieje kilka metod przetwarzania pracy inwentaryzacji ciągłej za pomocą programu Finance and Operations na urządzeniu przenośnym:

-   **Sterowane przez użytkownika** ─ Pracownik może określić identyfikator pracy inwentaryzacji ciągłej mającej stan **Otwarte**.
-   **Sterowane przez system** — Program Finance and Operations przypisuje identyfikator pracy inwentaryzacji ciągłej do pracownika.
-   **Grupowanie inwentaryzacji ciągłej** — Pracownik może grupować identyfikatory prac inwentaryzacji ciągłej, które są specyficzne dla danej lokalizacji, strefy lub puli pracy.
-   **Inwentaryzacja ciągła punktowa** — Pracownik może w dowolnym momencie zliczać towary w lokalizacji w magazynie bez tworzenia pracy inwentaryzacji ciągłej. W celu wykonania inwentaryzacji ciągłej punktowej w lokalizacji pracownik wprowadza identyfikator lokalizacji.

Poniższy przykład pokazuje sposób wykonania inwentaryzacji ciągłej punktowej za pomocą urządzenia przenośnego. Instrukcje widziane przez pracownika na urządzeniu zależą od ustawień menu inwentaryzacji ciągłej punktowej.

1.  Na urządzeniu przenośnym wybierz element menu do przetwarzania inwentaryzacji punktowej.
2.  Zarejestruj lokalizację, w której chcesz wykonać inwentaryzację ciągłą punktową.
3.  Zarejestruj i potwierdź numer towaru oraz zliczoną ilość towaru. **Uwaga:** Stan pracy inwentaryzacji ciągłej jest aktualizowany do wartości **Oczekiwanie na przegląd** lub **Zamknięte** na stronie **Cała praca**, zależnie od parametrów ustawionych na stronie **Pracownik**.
4.  Opcjonalnie: Powtórz krok 3 dla pozostałych towarów w lokalizacji i potwierdź, że nie są dostępne żadne dodatkowe towary do zliczania.

## Postępowanie z różnicami w inwentaryzacji ciągłej
<a id="resolve-cycle-counting-differences" class="xliff"></a>
Różnice w inwentaryzacji ciągłej występują w następujących scenariuszach, jeśli dla identyfikatora użytkownika pracy w opcji **Jest kierownikiem ds. inwentaryzacji ciągłej** ustawiono wartość **Nie**:

-   Zliczona wartość nie mieści się w granicach odchylenia określonych w polu **Maksymalny limit procentu** lub **Maksymalny limit ilości** na stronie **Użytkownicy pracy**. Na przykład ilość dostępnych zapasów w lokalizacji wynosi 50, a limit odchylenia dla użytkownika pracy wynosi 10. Różnica pojawi się, gdy użytkownik wprowadzi wartość, która nie mieści się w przedziale od 40 do 60.
-   Wartość zliczona różni się od ilości dostępnych zapasów, a nie ustawiono żadnych limitów odchyleń.

Na stronie **Inwentaryzacja cykliczna oczekuje na przegląd** można uzgodnić różnice zliczonej wartości, a następnie zaakceptować zliczoną wartość. Na stronie **Dostępne zapasy według lokalizacji** można zweryfikować zmodyfikowane obliczenie ilości towaru. Zliczona wartość jest odrzucana, jeśli różnicy nie można zatwierdzić.

# Informacje dodatkowe
<a id="see-also" class="xliff"></a>
[Konfigurowanie urządzeń przenośnych do pracy w magazynie](configure-mobile-devices-warehouse.md)




