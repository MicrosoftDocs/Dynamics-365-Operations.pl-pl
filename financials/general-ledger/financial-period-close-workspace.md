---
title: "Obszar roboczy zamknięcia okresu obrachunkowego"
description: "Ten artykuł zawiera omówienie obszaru roboczego Zamknięcie okresu obrachunkowego oraz pokrewnej konfiguracji."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Obszar roboczy zamknięcia okresu obrachunkowego

Ten artykuł zawiera omówienie obszaru roboczego Zamknięcie okresu obrachunkowego oraz pokrewnej konfiguracji.

Obszar roboczy zamknięcia okresu obrachunkowego

**Zamykanie okresów finansowych** obszar roboczy umożliwia śledzenie procesów finansowych zamknięcia całej firmy, obszarów i osoby. W zależności od widoku **zamykanie okresów finansowych** obszaru roboczego, zobaczysz albo wszystkich zadań i Stany harmonogramu zamknięcia lub tylko zadań, które są przypisane do użytkownika. 

Najpierw musisz wybrać harmonogram zamknięcia w górnej części obszaru roboczego. Wszystkie dane, które jest wyświetlane w obszarze roboczym są następnie filtrowane według harmonogramu wybranego zamknięcia.

### <a name="summary-tiles"></a>Kafelki podsumowania

Kafelki **Podsumowanie** oferują podgląd procesu, a wskaźniki pomagają zachować proces zamknięcia w odpowiednich torach. Są wyświetlane zadania, które zostały należne pozostałe zadania na dziś, zadania, które mają zostać wykonane dzisiaj, ale są blokowane ze względu na zależności i wszystkich pozostałych zadań dla procesu. Te informacje są dla wszystkich przedsiębiorstw, które są uwzględniane w harmonogramie wybranego zamknięcia.

### <a name="tasks-and-status-section"></a>Sekcja Zadania i stan

W **zadań i stanu** sekcji stan ogólny harmonogram zamknięcia jest w podziale na różne sposoby: stan przez firmy, stanu przez obszar i stan przez osobę odpowiedzialną. Można wyświetlić stan dla wszystkich zadań w zamykaniu zaplanować tylko zadania, które mają zostać wykonane dzisiaj, lub zadania, które są zaległe zmieniając filtr w górnej części listy kart. Można również wybrać filtr firmy, aby wyświetlić stan dla konkretnej firmy. Każda karta stan daje podział przez wartość procentową, która została zakończona i liczbę zadań, które pozostają. Kliknij kartę lub **szczegóły** Akcja filtrowania listy szczegółowych zadań przez zaznaczonej karty. 

Ostatnia karta jest dla listy zadań szczegółowych. Lista ta przedstawia pełną listę i mogą być filtrowane, tak aby pokazywał tylko zadania, które Cię interesują. Można filtrować listę zadań na kilka sposobów. Na przykład można filtrować przez zadanie datę ukończenia, spółki powiązanej oraz powiązanych obszaru. Możesz także pokazywanie lub ukrywanie ukończonych zadań na liście zadań. 

Dwa wskaźniki są używane do zadań:

-   Ikona wykrzyknika wskazuje, że zadanie jest zaległe. Dla zadań, które są zaległe termin jest wyróżnione kolorem czerwonym.
-   Ikona kłódki wskazuje, że zadanie zależy od innych zadań, które nie są jeszcze zakończone. Zadanie, które jest blokowany przez zależności nie można oznaczyć jako ukończone. Zależności dla zadania można ustawić za pomocą **ustawić zależności** akcji.

Nazwa zadania jest hiperłącze do usługi Microsoft Dynamics 365 dla operacji strony lub inne strony sieci Web, gdzie użytkownik musi przejść do zakończenia pracy. To hiperłącze można ustawić za pomocą **łącza do zadania** pola podczas edycji lub utworzyć zadanie. 

Do zadania można dołączyć pliki, notatek, obrazów i adresów URL za pomocą **załączniki** akcji. Można na przykład wskazać numerów arkuszy, które są używane jako część zadania, dodać komentarze na temat konkretnego zadania lub Dołącz plik raportu, który został wydrukowany dla zadania. Ikona pojawia się w **załącznika** kolumny dla zadania, gdy załącznik jest obecny. 

**Zadanie ukończone** musi być ręczne zaznaczona opcja po zakończeniu zadania. Gdy zadanie jest oznaczone jako ukończone, **zakończone data** pole jest automatycznie aktualizowane do bieżącej daty i godziny. Wskaźniki zależności są również aktualizowane.

## <a name="all-financial-period-close-tasks-list-page"></a>Strona listy wszystkich zadań zamknięcia okresu obrachunkowego
Można wyświetlić wszystkie bieżącego i poprzedniego okresu Zamknij zadania z **zadania zamknij wszystkie okresu finansowego** strony listy. Tej strony listy najlepiej nadaje się do historycznego analizy procesu zamykania, ponieważ zawiera on informacje o zaplanowanym termin płatności, Data rzeczywistego zakończenia i osoby, która wypełniła zadania. Informacje na tej stronie listę można łatwo wyeksportować do programu Microsoft Excel do raportowania i celów inspekcji.

## <a name="financial-period-close-configuration-page"></a>Strona konfiguracji zamknięcia okresu obrachunkowego
Przed użyciem **zamykanie okresów finansowych** obszaru roboczego, należy skonfigurować proces usługi Microsoft Dynamics 365 dla operacji za pomocą **finansowych konfiguracji zamknięcia okresu** strony. (Kliknij **księgi głównej**&gt;**zamknąć okres**&gt;**finansowych konfiguracji zamknięcia okresu**.)

### <a name="resources"></a>Zasoby

Na **zasobów** kartę, definiowania osób, które są zaangażowane w procesy zamknięcia. Najpierw należy przypisać tutaj każdego pracownika, który będzie odpowiedzialny za zadanie zamknięcia. Należy także określić pracownika widoku obszaru roboczego. Dostępne są następujące opcje:

-   **Tylko zadania przydzielone** — użytkownik będzie widział tylko zadania, które są przypisane do niego.
-   **Wszystkie zadania i stan** — użytkownik będzie widział wszystkie zadania zamknięcia i stan całego procesu.

Użytkownicy, którzy mają uprawnienia do wyświetlania tylko przydzielonych zadań nie mogą dodawać zadań do listy zadań, edytować zadań ani usuwać zadań z listy zadań.

### <a name="task-areas"></a>Obszary zadań

Za pomocą obszarów zadań można grupować zadania zamknięcia w logiczne obszary własności w obrębie organizacji. Obszarami zadań mogą być na przykład Rozrachunki z dostawcami, Rozrachunki z odbiorcami lub Księga główna.

### <a name="calendars"></a>Kalendarze

Tworzenie i edytowanie kalendarzy zamknięcia finansowego przy użyciu karty kalendarze.  To, gdzie będzie zdefiniować dni roboczych do zamykania procesów i będą używane do planowania zadań związanych z zamknięciem.  Utwórz nowy kalendarz i wskazać dni roboczych do stosowanego podczas planowania zadań.  Najlepiej utworzyć kalendarz obejmujący długi okres czasu, takie jak rok lub kilka lat, ponieważ można ją edytować po utworzeniu.  Po utworzeniu kalendarza, kliknij przycisk Edytuj, aby zaktualizować kalendarz dla określonych dni, takie jak dni wolne od pracy.  Zamykanie zadania będą planowane w dniach, kiedy wartość w formancie jest równa Open.  Jeśli zadania zamknięcia nie powinno być harmonogram na określony dzień, dzień ten powinien mieć wartość formantu ustawiony na zamknięty.

### <a name="templates"></a>Szablony

Finansowe szablon Zamknij Umożliwia zdefiniowanie wszystkich zadań, które są częścią procesu zamykania. Zadanie zamknięcia jest cykliczne nakładu pracy, która jest przypisana do indywidualnego do wykonania w ramach każdego procesu zamykania. W szablonie należytym względnej daty muszą być zdefiniowane dla każdego zadania zamknięcia. Względne należytym Data jest liczba dni przed lub po dacie zakończenia okresu zdefiniowanego, który zadanie ma zostać ukończone każdego okresu. Godzina realizacji jest przypisany do każdego zadania. Godzina realizacji jest ustawiona przy użyciu kontekstu strefę czasową i zostaną przekonwertowane na strefę czasową dla każdego użytkownika. 

Jedna lub więcej spółek, w których stosuje się to zadanie można przypisać zadanie w szablonie. Jeśli inna osoba jest przypisany do ukończenia tego nakładu pracy w każdej firmie, może znaleźć przydatne do tworzenia wielu zadań dla samego nakładu pracy. Utwórz jedno zadanie dla każdej firmy. 

**Łącza do zadania** element menu jest skojarzony z nakładu pracy zadania i może służyć do przejść bezpośrednio do strony skojarzone z łącza zadań w obszarze roboczym. Na przykład zadanie zamknięcia, aby uruchomić proces przeszacowania waluty dla rozrachunków z dostawcami mogą być połączone ze skojarzonymi z nimi **przeszacowanie w walucie obcej** strony w programie Microsoft Dynamics 365 dla operacji. Można również utworzyć łącze do zewnętrznego adresu URL. 

> [! Wskazówka] Jeśli chcesz powiązać z określonego raportu Management Reporter okresu finansowego zamykanie zadania, można użyć adresu URL raportu. Aby uzyskać dostęp do adresu URL raportu, otwórz raport w programie report designer, a następnie kliknij **pliku**&gt;**wyświetlić raport** aby otworzyć raport w przeglądarce sieci web. Można następnie skopiować adres URL w pasku adresu przeglądarki i wkleić go w polu **URL** **łącza zadania**. 

W szablonie można zdefiniować współzależności zadań. Jeśli zadania została ustawiona na jedno lub więcej zadań, zadania nie można oznaczyć jako ukończone, dopóki wszystkie zależności zostały zakończone. 

Można utworzyć wiele szablonów Zamknij finansowych. Następnie można użyć różnych szablonów, do śledzenia procesów zamknięcia dla różnych typów okresów, takich jak koniec miesiąca lub koniec roku, lub do śledzenia firm używających zamknięciu różnych procesów. Po utworzeniu jednego szablonu można skopiować go do nowego szablonu i wprowadź wymagane zmiany. Tylko jeden szablon można przypisać do każdego zamknięcia harmonogramu.

### <a name="closing-schedules"></a>Harmonogramy zamknięcia

Harmonogram zamknięcia umożliwia przypisywanie finansowych Zamknij szablon do określonego okresu finansowego, który musi zostać zamknięty. Zadania z szablonu następnie są automatycznie generowane dla określonego okresu, a nowy harmonogram zamknięcia jest dodawany do obszaru roboczego. Podczas tworzenia nowego harmonogramu zamknięcia, **Data końcowa okresu** pola jest używana do określenia rzeczywistego ukończenia dat zadań zamknięcia, oparte na stosownym względne Data jest przypisany w finansowych Zamknij szablon. 

Przydzielić kalendarz odpowiednie zamknięcia harmonogramu, aby wskazać dni roboczych stosowaną w przypadku planowania zadań. Jeżeli nie zdefiniujesz wybranego kalendarza, zadania należne daty będą używać wszystkich dni tygodnia. 

Należy także zdefiniować firm, które mają zostać skojarzone z harmonogramem zamknięcia. Jeśli szablon zadania są przydzielane do wielu firm, oddzielne zadania zostanie utworzone dla każdej firmy, która jest w harmonogramie zamknięcia i przypisane do tego zadania szablonu. 

Po zakończeniu harmonogramu zamknięcia, zaznacz **zamknięty** opcji dla niego. Historia zadań będą nadal dostępne z **zadania zamknij wszystkie okresu finansowego** strony listy, ale harmonogram zamknięcia zostaną usunięte z obszaru roboczego. Po harmonogramu zamknięcia zostało oznaczone jako **zamknięty**, użytkownik nie będzie mógł dodawać zadania do niego, edytować zadania lub usunięcia zadania z niego.


