---
title: "Obszar roboczy zamknięcia okresu obrachunkowego"
description: "Ten artykuł zawiera omówienie obszaru roboczego Zamknięcie okresu obrachunkowego oraz pokrewnej konfiguracji."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 5de5e3aad0b7a5853653ae53326dac078ec94fea
ms.contentlocale: pl-pl
ms.lasthandoff: 06/20/2017


---

# Obszar roboczy zamknięcia okresu obrachunkowego
<a id="financial-period-close-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie obszaru roboczego Zamknięcie okresu obrachunkowego oraz pokrewnej konfiguracji.

Obszar roboczy zamknięcia okresu obrachunkowego

Obszar roboczy **Zamknięcie okresu obrachunkowego** umożliwia śledzenie procesów zamknięcia finansowego różnych firm, obszarów i osób. W zależności od widoku obszaru roboczego **Zamknięcie okresu obrachunkowego** będą widoczne albo wszystkie zadania i stany dla harmonogramu zamknięcia, albo tylko zadania, które są przypisane do Ciebie. 

Należy najpierw wybrać harmonogram zamknięcia w górnej części obszaru roboczego. Wszystkie dane, które są widoczne w obszarze roboczym, są następnie filtrowane według wybranego harmonogramu zamknięcia.

### Kafelki podsumowania
<a id="summary-tiles" class="xliff"></a>

Kafelki **Podsumowanie** oferują podgląd procesu, a wskaźniki pomagają zachować proces zamknięcia w odpowiednich torach. Można wyświetlić zadania, które są zaległe, pozostałe zadania na dziś, zadania, które mają zostać wykonane dzisiaj, ale są zablokowane ze względu na zależności, oraz wszystkie pozostałe zadania procesu. Te informacje dotyczą wszystkich firm, które są uwzględniane w wybranym harmonogramie zamknięcia.

### Sekcja Zadania i stan
<a id="tasks-and-status-section" class="xliff"></a>

W sekcji **Zadania i stan** ogólny harmonogramu zamknięcia daje się podzielić na różne sposoby: stan według firmy, stan według obszaru oraz stan według osoby odpowiedzialnej. Można wyświetlić stan dla wszystkich zadań w harmonogramie zamknięcia, tylko zadania, które mają zostać wykonane dzisiaj, lub zadania, które są zaległe, przez zmianę filtru u góry listy kart. Można również wybrać filtr firm, aby wyświetlić stan dla określonej firmy. Każda karta stanu pokazuje podział według procentu ukończenia oraz według liczby pozostałych zadań. Kliknij kartę lub akcję **Wyświetl szczegóły**, aby wyfiltrować szczegółową listę zadań według wybranej karty. 

Na ostatniej karcie jest szczegółowa lista zadań. Ta lista przedstawia pełną listę zadań i może być filtrowana, aby pokazywać tylko interesujące Cię zadania. Listę zadań można filtrować na kilka sposobów. Na przykład można filtrować według zadań, dat wykonania, skojarzonej firmy i skojarzonego obszaru. Można również wybrać wyświetlanie lub ukrywanie ukończonych zadań na liście zadań. 

Dwa wskaźniki są używane do zadań:

-   Ikona wykrzyknika wskazuje, że zadanie jest zaległe. W przypadku zadań, które są zaległe, data wykonania jest wyróżniona kolorem czerwonym.
-   Ikona kłódki wskazuje, że zadanie zależy od innych zadań, które nie są jeszcze zakończone. To zadanie jest zablokowane przez zależności i nie można oznaczyć go jako zakończonego. Zależności zadania można ustawić za pomocą akcji **Ustaw zależność**.

Nazwa zadania jest hiperłączem do strony programu Microsoft Dynamics 365 for Operations lub innej strony sieci Web, na którą użytkownik musi przejść, aby ukończyć pracę. To hiperłącze można ustawić za pomocą pola **Łącze zadania** podczas edytowania lub tworzenia zadania. 

Do zadania można dołączać pliki, notatki, obrazy i adresy URL za pomocą akcji **Załączniki**. Na przykład można wskazać numery arkuszy używanych w ramach zadania, dodać komentarze dotyczące konkretnego zadania lub dołączyć plik raportu, który był drukowany dla zadania. Ikona pojawia się w kolumnie **Załącznik** dla zadania, jeśli załącznik jest obecny. 

Opcję **Zadanie ukończone** należy zaznaczyć ręcznie po ukończeniu zadania. Gdy zadanie jest oznaczone jako ukończone, pole **Data zakończenia** jest automatycznie aktualizowane na bieżącą datę i godzinę. Również wskaźniki zależności są odpowiednio aktualizowane.

## Strona listy wszystkich zadań zamknięcia okresu obrachunkowego
<a id="all-financial-period-close-tasks-list-page" class="xliff"></a>
Wszystkie zadania zamknięcia bieżącego i poprzedniego okresu można wyświetlić na stronie listy **Wszystkie zadania zamknięcia okresu obrachunkowego**. Ta strona listy najlepiej nadaje się do historycznej analizy procesu zamknięcia, ponieważ zawiera informacje o zaplanowanej dacie wykonania, dacie rzeczywistego zakończenia i osobie, która ukończyła zadanie. Informacje na tej stronie listy można łatwo wyeksportować do programu Microsoft Excel do celów raportowania i inspekcji.

## Strona konfiguracji zamknięcia okresu obrachunkowego
<a id="financial-period-close-configuration-page" class="xliff"></a>
Aby można było używać przestrzeni roboczej **Zamknięcie okresu obrachunkowego**, należy skonfigurować proces w programie Microsoft Dynamics 365 for Finance and Operations za pomocą strony **Konfiguracja zamknięcia okresu obrachunkowego**. (Kliknij kolejno opcje **Księga główna** &gt; **Zamknięcie okresu** &gt; **Konfiguracja zamknięcia okresu obrachunkowego**).

### Zasoby
<a id="resources" class="xliff"></a>

Na karcie **Zasoby** definiuje się osoby, które są zaangażowane w procesy zamknięcia. Najpierw należy przypisać tutaj dowolnego pracownika, który będzie odpowiedzialny za zadanie zamknięcia. Należy także określić widok obszaru roboczego pracownika. Dostępne są następujące opcje:

-   **Tylko zadania przydzielone** — użytkownik będzie widział tylko zadania, które są przypisane do niego.
-   **Wszystkie zadania i stan** — użytkownik będzie widział wszystkie zadania zamknięcia i stan całego procesu.

Użytkownicy, którzy mają uprawnienia do wyświetlania tylko przydzielonych zadań nie mogą dodawać zadań do listy zadań, edytować zadań ani usuwać zadań z listy zadań.

### Obszary zadań
<a id="task-areas" class="xliff"></a>

Za pomocą obszarów zadań można grupować zadania zamknięcia w logiczne obszary własności w obrębie organizacji. Obszarami zadań mogą być na przykład Rozrachunki z dostawcami, Rozrachunki z odbiorcami lub Księga główna.

### Kalendarze
<a id="calendars" class="xliff"></a>

Można tworzyć i edytować kalendarze zamknięcia finansowego za pomocą karty Kalendarze.  W tym miejscu definiuje się dni robocze procesów zamknięcia, które będą używane do planowania zadań związanych z zamknięciem.  Można utworzyć nowy kalendarz i wskazać dni robocze, które będą używane do planowania zadań.  Najlepiej utworzyć kalendarz obejmujący dłuższy czas, np. rok lub kilka lat, ponieważ po utworzeniu można go edytować.  Po utworzeniu kalendarza kliknij przycisk Edytuj, aby zaktualizować kalendarz dla określonych dni, np. wolnych od pracy.  Zadania zamknięcia będą planowane według dni, dla których opcja Kontrola ma wartość Otwarte.  Jeśli zadania zamknięcia nie powinny być zaplanowane na określony dzień, ten dzień powinien mieć w opcji Kontrola wartość Zamknięte.

### Szablony
<a id="templates" class="xliff"></a>

Za pomocą szablonu zamknięcia finansowego można zdefiniować wszystkie zadania, które są częścią procesu zamknięcia. Zadanie zamknięcia jest pracą cykliczną, która jest przypisywana do osoby w celu wykonania podczas każdego procesu zamknięcia. W szablonie względna data wykonania musi być zdefiniowana dla każdego zadania zamknięcia. Względna data wykonania to liczba dni przed lub po zdefiniowanej dacie zakończenia okresu, kiedy zadanie musi zostać ukończone dla tego okresu. Godzina wykonania jest również przypisywana do każdego zadania. Godzinę wykonania ustawia się w kontekście strefy czasowej administratora i jest ona konwertowana na strefy czasowe poszczególnych użytkowników. 

Zadanie w szablonie można przypisać do jednego lub kilku firm, do których stosuje się to zadanie. Jeśli inna osoba jest przypisana do ukończenia tej pracy w każdej firmie, pomocne może być utworzenie wielu zadań dla tej samej pracy. Utwórz jedno zadanie dla każdej firmy. 

Element menu **Łącze do zadania** jest skojarzone z nakładem pracy i pozwala przejść bezpośrednio do skojarzonej strony z łącza zadania w obszarze roboczym. Na przykład zadanie zamknięcia służące do realizacji procesu przeszacowania waluty w module Rozrachunki z dostawcami może być połączone ze stroną **Przeszacowanie w walucie obcej** w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Można również utworzyć łącze do zewnętrznego adresu URL. 

> [Wskazówka[ Aby utworzyć łącze pomiędzy raportem programu Management Reporter a zadaniem zamknięcia okresu obrachunkowego, można użyć adresu URL raportu. Aby uzyskać dostęp do adresu URL raportu, otwórz raport w projektancie raportów i kliknij kolejno opcje **Plik** &gt; **Wyświetl raport**, a raport zostanie otwarty w przeglądarce internetowej. Można następnie skopiować adres URL w pasku adresu przeglądarki i wkleić go w polu **URL** **łącza zadania**. 

W szablonie można zdefiniować współzależności zadań. Jeśli zadanie zostało skonfigurowane jako zależne od jednego lub kilku zadań, to zadanie nie można być oznaczone jako zakończone do momentu zakończenia wszystkich zależności. 

Można utworzyć wiele szablonów zamknięcia finansowego. Różnych szablonów można następnie używać do śledzenia procesów zamknięcia dla różnych typów okresów, np. na koniec miesiąca lub na koniec roku, lub do śledzenia firm korzystających z różnych procesów zamknięcia. Po utworzeniu jednego szablonu można skopiować go do nowego szablonu i wprowadzić wymagane zmiany. Do każdego arkusza zamknięcia można przypisać tylko jeden szablon.

### Harmonogramy zamknięcia
<a id="closing-schedules" class="xliff"></a>

Harmonogram zamknięcia umożliwia przypisanie szablonu zamknięcia finansowego do określonego okresu obrachunkowego, który musi zostać zamknięty. Zadania z wybranego szablonu są następnie generowane automatycznie w podanym okresie, a nowy harmonogram zamknięcia jest dodawany do obszaru roboczego. Podczas tworzenia nowego harmonogramu zamknięcia pole **Data końcowa okresu** pozwala określić rzeczywiste daty wykonania dla zadań zamknięcia w oparciu o względną datę wykonania, która jest przypisana w szablonie zamknięcia finansowego. 

Przypisz kalendarz odpowiedni dla harmonogramu zamknięcia, aby wskazać dni robocze do użycia w przypadku planowania zadań. Jeśli nie zdefiniowano konkretnego kalendarza, daty wykonania zadań będą używały wszystkich dni tygodnia. 

Należy także zdefiniować firmy, które mają zostać skojarzone z harmonogramem zamknięcia. Jeśli zadania szablonu są przypisane do wielu firm, oddzielne zadania zostaną utworzone dla każdej firmy figurującej w harmonogramie zamknięcia i przydzielone do zadania szablonu. 

Po wykonaniu harmonogramu zamknięcia wybierz dla niego opcję **Zamknięty**. Historia zadań nadal będzie dostępna ze strony listy **Wszystkie zadania zamknięcia okresu obrachunkowego**, ale harmonogram zamknięcia zostanie usunięty z obszaru roboczego. Po oznaczeniu harmonogramu zamknięcia jako **Zamknięty** nie będzie można dodawać do niego zadań, edytować zadań ani usuwać zadań.




