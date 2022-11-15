---
title: Ustawianie planów głównych
description: W tym artykule opisano różne ważne strategie i parametry używane do konfigurowania planowania głównego.
author: t-benebo
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 150e02916e056946016155d1b4969e99fbd47af5
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740665"
---
# <a name="set-up-master-plans"></a>Ustawianie planów głównych

[!include [banner](../includes/banner.md)]

W tym artykule opisano różne ważne strategie i parametry używane do konfigurowania planowania głównego. Zawiera omówienie typów planów używanych przez planowanie główne oraz wyjaśnienie, które strategie planu należy stosować w zależności od wymagań biznesowych. Opisano tu także główne parametry wpływające na plan i wyjaśniające, w jaki sposób te parametry wpływają na sugerowane zamówienia planowane.

## <a name="types-of-master-plans"></a>Typy planów głównych

Planowanie główne ma dwa typy planów: statyczne i dynamiczne. Każdy typ jest przeznaczony do innego użytku. W celu uzyskania najlepszej wydajności zaleca się użycie odpowiedniego planu w danym scenariuszu.

### <a name="static-plan"></a>Plan statyczny

Plan statyczny pozostaje niezmieniony, niezależnie od zmian podaży i popytu aż do następnego uruchomienia planowania głównego.

Plan statyczny służy do zatwierdzania i ustalania sugerowanych zamówień. Jest to plan operacyjny, z którego mogą korzystać różne osoby związane z firmą (takie jak nabywca lub pracownik z działu planowania produkcji), aby uprościć proces decydowania i przeprowadzać codzienne czynności i działania.

Ponadto plan statyczny obsługuje regenerację. Całkowicie nowy zoptymalizowany plan jest obliczany przy każdym uruchomieniu planowania głównego, a istniejące niezatwierdzone zamówienia są usuwane.

### <a name="dynamic-plan"></a>Plan dynamiczny

Plan dynamiczny zazwyczaj rozpoczyna się jako kopia planu statycznego, ale może być aktualizowany za każdym razem, gdy zmieniają się dane główne. Na przykład, jeśli dane zmienią się, tworzone jest nowe zamówienie sprzedaży.

Plan dynamiczny jest używany do planowania ad hoc. Ta funkcjonalność umożliwia firmie monitorowanie zmieniającej się sieci zamówień i dostępności towarów bez zakłócania planu statycznego, którego używają inni użytkownicy w swoich procesach roboczych. Jest on szczególnie stosowany w możliwych do zrealizowania (CTP). Plan dynamiczny jest planem domyślnym, gdy zapotrzebowanie netto jest otwierane ze stron zamówienia (takich jak zamówienie sprzedaży, zamówienie zakupu lub strony zlecenia produkcyjnego).

W planie dynamicznym jest używana zmiana netto. Dzięki temu gwarantuje krótszy czas pracy.

## <a name="strategies-for-using-master-plans"></a>Strategie używania planów głównych

W planowaniu głównym można zastosować jeden plan lub dwa plany. Stosowana strategia zależy od wymagań biznesowych użytkownika.

### <a name="one-plan-strategy"></a>Strategia o jednym planie

W przypadku strategii z jednym planem jest używany ten sam plan główny dla planu statycznego i planu dynamicznego. Ta strategia jest używana w scenariuszach tworzenia zapasów, gdzie zazwyczaj nie jest konieczne symulowanie planu, który planuje realizację zamówienia.

Strategia jednego planu jest zazwyczaj stosowana w przemyśle detalicznym i dystrybucji lub w przypadku potwierdzenia dat dostawy sprzedaży na podstawie umów dotyczących poziomu usług (SLAs) lub czasów realizacji. W przypadku planu Kontrola daty dostawy może być używana bez określenia CTP.

Jeśli trzeba wykonać symulację, można ponownie uruchomić plan dla towarów, które wymagają symulacji. Planowane zamówienia są zazwyczaj ustalane na wyprodukowanie symulacji zamówienia.

### <a name="two-plan-strategy"></a>Strategia o dwóch planach

W przypadku strategii z dwoma planami używany jest plan statyczny i inny plan dynamiczny. Strategia dwuplanowa jest zazwyczaj używana do tworzenia scenariuszy „konfiguracja na zamówienie” i „produkcja na zamówienie”, gdzie trzeba wykonywać symulacje zamówień sprzedaży i obliczać dokładne daty dostawy zamówień sprzedaży, ale obliczenia nie mogą wpływać na codzienne operacje. Symulacje są zawsze wykonywane w planie dynamicznym. Strategia dwuplanowa jest przydatna na przykład w przemyśle samochodowym i producentach OEM.

W przypadku strategii dwuplanowej można użyć kontroli daty dostawy CTP. W przypadku korzystania z CTP system automatycznie wyzwala przebieg w planie dynamicznym.

### <a name="setting-up-the-plans"></a>Konfigurowanie planów

Plany można tworzyć na stronie **plany główne** (**Planowanie główne \> Ustawienia \> Plany \> Plany główne**).

Można określić, które plany będą używane dla planu statycznego i planu dynamicznego, ustawiając pola **Bieżący główny plan statyczny** i **Bieżący główny plan dynamiczny** na stronie **parametrów planowania głównego** (**Planowanie główne \> Ustawienia \> Parametry planowiania głównego**). Aby zastosować strategię z jednym planem, należy wybrać ten sam plan w polach **Bieżący statyczny plan główny** i **Bieżący dynamiczny plan główny**.

## <a name="types-of-planning-methods"></a>Typy metod planowania

Do uruchomienia planowania głównego można użyć trzech metod obliczania: Regeneracja i zmiana netto. W każdej metodzie jest tworzony inny plan, gdy jest uruchamiany.

Metoda planowania jest określana w oknie dialogowym **przebieg planowania głównego**. By otworzyć to okno dialogowe, przejdź do **Planowania głównego \> planowania głównego \> Uruchom \> Planowania głównego** lub wybierz opcję **Uruchom** w obszarze roboczym **Planowanie główne**.

### <a name="regeneration"></a>Ponowne generowanie

Metoda planowania regeneracji usuwa istniejące zamówienia planowane, chyba że zostały potwierdzone. Powoduje to wygenerowanie nowych zamówień planowanych na podstawie wszystkich zapotrzebowań. Regeneracja jest jedyną metodą planowania, która jest dostępna dla planów statycznych.

- Uwzględnia się zmiany w dostawie. Zmiany te obejmują zmiany prognozy.
- Ta metoda uwzględnia kod zapotrzebowania na **okresy**.
- Ta metoda obsługuje funkcję podstawiania produktów (PI).

### <a name="net-change"></a>Zmiana netto

Metoda planowania zmian netto generuje zamówienia planowane w celu pokrycia zapotrzebowania, które zostały utworzone lub zmienione od czasu ostatniego uruchomienia planowania głównego. Zmiany w dostawie nie są brane pod uwagę przy uruchamianiu tej metody. System nie rozważa żadnych nowych dostaw, a wcześniej utworzone zamówienia planowane nie są usuwane, jeśli nie są już wymagane. Metoda planowania zmian netto działa szybciej niż Metoda regenerowania. Jest ona dostępna tylko w przypadku planów dynamicznych.

- Daty akcji i prognozy są aktualizowane dla wszystkich wymagań.
- Ta metoda nie uwzględnia kodu zapotrzebowania na **okresy**.
- Ta metoda nie spełnia prognozy, nawet jeśli jest wybrana w planie.
- Ta metoda nie obsługuje funkcji podstawiania produktów (PI).

### <a name="net-change-minimized"></a>Zminimalizowana zmiana netto

Metoda zminimalizowanego planowania zmian netto generuje zamówienia planowane w celu pokrycia tylko zapotrzebowania, które zostały utworzone lub zmienione od czasu ostatniego planowanego uruchomienia planowania głównego. W przypadku tej metody, w przeciwieństwie do metody zmiany netto, daty akcji i daty prognoz są aktualizowane tylko dla nowych lub zmienionych wymagań. Ta metoda planowania jest dostępna tylko w przypadku planów dynamicznych.

## <a name="types-of-scheduling-methods"></a>Typy metod planowania

Dla każdego planu, na **głównej** skróconej karcie strony **Planów głównych** (**Planowanie główne \> Ustawienia \> Plany \> Plany główne**) należy wybrać metodę planowania używaną do zamówień produkcji. Produkcję można planować na poziomie operacji i zadań.

### <a name="operations-scheduling"></a>Planowanie operacji

Funkcji planowania operacji można używać, aby przedstawić ogólne oszacowanie procesu produkcji w wybranym okresie. Planowanie operacji nie powoduje rozłożenia operacji marszruty produkcji w zadania. Aby uzyskać więcej informacji na temat planowania operacji , należy zapoznać się z tematem [Planowanie operacji](/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Planowanie zadań

Planowanie zadań jest bardziej szczegółową metodą planowania, w której każda operacja jest dzielona na poszczególne zadania lub zadania. Planowanie zadań obejmuje informacje dotyczące zdolności produkcyjnych. Zazwyczaj służy ono do planowania poszczególnych zadań na produkcji w perspektywie czasowej bieżącej lub krótkoterminowej. Aby uzyskać więcej informacji na temat planowania zadań, należy zapoznać się z tematem [Planowanie zadań](/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Horyzonty czasowe w dniach

Dla każdego planu można określić, jak daleko w przyszłości mają być obliczane różne zapotrzebowania i inne aspekty w planowaniu głównym. Okres jest określany jako *horyzont czasowy*. W celu uzyskania najlepszej wydajności planowania głównego zaleca się dostosowanie różnych horyzontów czasowych, tak aby spełniały wymagania biznesowe użytkownika. Dla każdego planu można odszukać horyzonty czasowe na skróconej karcie **horyzonty czasowe w dniach** na stronie **Plany główne** (**Planowanie główne \> Ustawienia \> Plany \> Plany główne**).

> [!NOTE]
> Horyzonty czasowe określają, jak daleko w przyszłości różne obliczenia i inne okoliczności muszą być obliczane przez planowanie główne. Horyzonty czasowe wybrane na tej stronie zastąpią horyzonty czasowe zdefiniowane w grupie zapotrzebowania. Oznacza to ustawienie opcji horyzontu czasowego na wartość „tak”, a zdefiniowanie dni spowoduje zastąpienie horyzontu czasowego zdefiniowanego w grupie zapotrzebowania. Po ustawieniu opcji na wartość „nie” horyzont czasowy zostanie zdefiniowany w grupie zapotrzebowania. Na koniec, jeśli użytkownik nie chce używać opcji (na przykład nie chce używać komunikatów akcji), należy ją skonfigurować na wartość **tak**, a następnie skonfigurować horyzont czasowy na **0** (zero) dni.

### <a name="coverage"></a>Zapotrzebowanie

Horyzont czasowy zapotrzebowania reprezentuje okres planowania lub stopień uwzględnienia popytu. Innymi słowy wskazuje zakres planowania.

Ustawienie opcji **zapotrzebowania** na wartość **tak** powoduje, że można zastąpić horyzont czasowy zapotrzebowania zdefiniowany dla towaru podczas planowania głównego. W takim przypadku należy wprowadzić liczbę dni, dla których w planowaniu głównym powinny być uwzględnione zapotrzebowania. Horyzont czasowy zapotrzebowania jest obliczany od daty bieżącej do przodu. Zawsze są przetwarzane zapotrzebowania z datą wcześniejszą od daty bieżącej.

> [!NOTE]
> W celu uzyskania najlepszej wydajności planowania głównego zaleca się dostosowanie zapotrzebowanie horyzontów czasowych do planowania horyzontów.

### <a name="freeze"></a>Zamrożenie

Horyzont czasowy zamrożenia reprezentuje okres, w którym istniejące planowane zamówienia nie ulegają zmianie po uruchomieniu nowego planu głównego. Planowane zamówienia są zamrożone, a nowe planowane zamówienia nie będą mogły zostać sugerowane.

Ustawienie opcji **Zamrożenia** na wartość **tak** umożliwia nadpisane zamrożenia horyzontu czasowego zapotrzebowania zdefiniowanego dla towaru podczas planowania głównego. W takim przypadku należy wprowadzić liczbę dni, podczas których działanie planowania powinno być zamrożone. Należy pamiętać, że w tym okresie nie będą generowane nowe planowane zamówienia, a istniejące planowane zamówienia nie będą mogły zostać zmienione.

### <a name="firming"></a>Akceptacja

Horyzont czasowy ustalania wskazuje horyzont czasowy, w którym zamówienia planowane są automatycznie konwertowane na zamówienia produkcyjne i zakupu. Ten proces jest również określany jako *automatyczne akceptowanie planowanych zamówień*.

Ustawienie opcji **Akceptowania** na wartość **tak** umożliwia nadpisane zaakceptowanego horyzontu czasowego zapotrzebowania zdefiniowanego dla towaru podczas planowania głównego. W takim wypadku należy wprowadzić liczbę dni, w których planowane zamówienia zakupu i sprzedaży powinny być automatycznie ustalane. Ten horyzont czasowy akceptowania jest obliczany od daty planowania głównego do przodu. Aby możliwe było automatyczne ustalanie planowanego zamówienia zakupu, towar musi być skojarzony z dostawcą.

### <a name="forecast-plan"></a>Plan wg prognozy

Horyzont czasowy planu prognozy wskazuje, jak daleko w przyszłym planowaniu głównym tworzy zamówienia planowane dla towarów, które mają prognozowany popyt.

Ustawienie opcji **Plan prognoz** na wartość **tak** powoduje, że można zastąpić horyzont czasowy planu progmozy, który został zdefiniowany dla towaru podczas planowania głównego. W takim przypadku należy wprowadzić liczbę dni, dla których prognoza sprzedaży z planu według prognozy powinna być uwzględniana w planowaniu głównym.

### <a name="capacity"></a>Zdolności produkcyjne

Horyzont czasowy zdolności produkcyjnych wskazuje, jak daleko w przyszłości system uwzględnia maksymalne zdolności produkcyjne zasobów podczas planowania zamówień. Innymi słowy, plan planuje zlecenia produkcyjne przy użyciu marszruty produkcji dla towarów i uwzględnia zasoby marszruty produkcji oraz maksymalne zdolności produkcyjne poszczególnych zasobów.

Ustawienie opcji **Pojemność** na wartość **tak** powoduje, że można zastąpić pojemność horyzontu czasowego zapotrzebowania zdefiniowanego dla towaru podczas planowania głównego. W takim przypadku wprowadź liczbę dni, na które mają być planowane zdolności produkcyjne dla planowanych zleceń produkcyjnych. Podczas planowania głównego używana jest aktywna marszruta produkcji towaru i wykonywane jest planowanie wstecz od daty zapotrzebowania. Jeśli data zapotrzebowania dla planowanego zlecenia produkcyjnego przypada poza horyzontem czasowym zdolności produkcyjnych, podstawą do określenia czasu realizacji jest czas dostawy towaru. Horyzont czasowy pojemności jest obliczany od daty bieżącej do przodu.

### <a name="action-message"></a>Komunikat akcji

Komunikaty akcji sugerują zmiany, które można wprowadzać w istniejącym zamówieniu dostawy w celu ułatwienia optymalizacji planu dostaw. Może to być na przykład zaproponowanie zaawansowania lub przełożenia zamówień, a także zwiększenie lub zmniejszenie ilości zamówienia.

Ustawienie opcji **Komunikat akcji** na wartość **tak** powoduje, że można zastąpić komunikat akcji horyzontu czasowego, który został zdefiniowany dla towaru podczas planowania głównego. Jeśli ta opcja jest wybrana, należy wprowadzić liczbę dni, dla których w planowaniu głównym będą generowane komunikaty akcji dotyczące zapotrzebowania. Komunikat akcji horyzontu czasowego pojemności jest obliczany od daty bieżącej do przodu.

Aby uzyskać więcej informacji o komunikatach akcji, zapoznaj się z [komunikatami akcji](/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> Obliczanie komunikatów akcji powoduje dłuższy czas pracy planowania głównego. Jeśli komunikaty akcji nie są regularnie analizowane i stosowane (codziennie, co tydzień itd.), należy rozważyć wyłączenie obliczeń podczas przebiegu planowania głównego Aby wyłączyć obliczanie, na stronie **Plany główne** ustaw wartość w polu horyzont czasowy **komunikatu akcji** na **0** (zero) dla planu głównego, który jest uruchomiony. Upewnij się również, że ustawienie **Komunikatu akcji** jest wyłączone dla wszystkich grup zapotrzebowania.

### <a name="calculated-delays"></a>Obliczone opóźnienia

Można określić, jak daleko w przyszłości mają być wykrywane i raportowane przyszłe możliwe opóźnienia w planowanych zamówieniach. W ten sposób można planować możliwe (opóźnione) daty dostawy.

Jeśli planowane zamówienie nie może być spełnione dla żądanej daty, jest ono planowane jako Najwcześniejsza data realizacji dla transakcji na podstawie czasów realizacji oraz dostępności materiałów i zdolności produkcyjnych.

### <a name="approved-requisitions-time-fence"></a>Zatwierdzony horyzont czasowy zapotrzebowań

Planowanie główne można skonfigurować w celu utworzenia zamówień planowanych dla zapotrzebowania na zapotrzebowanie. Skonfiguruj opcję **Uwzględnij zapotrzebowanie** na **Tak** w skróconej karcie **Ogólne** na stronie **Plany główne**. Następnie, jeśli cel zaakceptowanego zapotrzebowania jest uzupełnieniem zapasów, planowanie główne automatycznie utworzy odpowiadające mu zamówienie planowane w celu jego realizacji. Metodę uzupełnienia określają zasady zaopatrzeniowe skonfigurowane dla towarów w organizacji. Po utworzeniu i zatwierdzeniu zapotrzebowania na uzupełnienie nie są konieczne żadne dodatkowe działania użytkownika.

Ustawienie opcji **Zatwierdzony horyzont czasowy** na wartość **tak** w skróconej karcie **horyzonty czasowe w dniach** umożliwia zastąpienie zatwierdzonego horyzontu czasowego zapotrzebowań zdefiniowanego dla towaru podczas planowania planu głównego. W takim przypadku należy wpisać liczbę dni w przeszłości, dla których popyt z zatwierdzonych zapotrzebowań oznaczonych celem Uzupełnianie zapasów ma być uwzględniany w planowaniu głównym. Na przykład można określić, że powinny być uwzględniane i planowane tylko niezrealizowane, zaległe żądania ze strony zatwierdzonych zapotrzebowań, które zostały utworzone w ciągu ostatnich 10 dni.

### <a name="sequencing"></a>Harmonogram

Sekwencjonowanie umożliwia rozmieszczanie zamówień planowanych na podstawie atrybutów harmonogramu skojarzonych z gotowym produktem. Jest on często używany do przygotowywania zleceń produkcyjnych do pakowania. Na przykład można go użyć do pakowania pudeł w określonej kolejności na podstawie koloru i rozmiaru.

Ustawienie opcji **sekwencjonowania** na wartość **Tak** powoduje, że można określić, jak daleko w przyszłości operacje mają być sekwencjonowane. Należy pamiętać, że im większy horyzont czasowy, tym dłużej będzie wykonywane planowanie główne.

### <a name="calculated-delays"></a>Obliczone opóźnienia

Opcje opóźnienia pomagają zagwarantować, że zamówienia mają wykonalne daty planowane. Następujące opcje są dostępne na skróconej karcie **Obliczonych opóźnień** na stronie **Plany główne**:

- **Upewnij się, że planowane zamówienia nie są tworzone przed datą rozpoczęcia planowania głównego** — ustawienie tej opcji na wartość **tak**, aby zagwarantować, że zamówienia nie będą planowane dla dat w przeszłości.
- **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w obszarze **planowane zamówienia zakupu**) — ustawienie tej opcji na wartość **tak** powoduje dodanie obliczonego opóźnienia do zapotrzebowania.
- **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w obszarze **planowane zamówienia produkcji**) — ustawienie tej opcji na wartość **tak** powoduje dodanie obliczonego opóźnienia do zapotrzebowania.
- **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w obszarze **planowany transfer**) — ustawienie tej opcji na wartość **tak** powoduje dodanie obliczonego opóźnienia do zapotrzebowania.
- **Dodaj obliczone opóźnienie do daty zapotrzebowania** (w obszarze **planowany Kanban**) — ustawienie tej opcji na wartość **tak** powoduje dodanie obliczonego opóźnienia do zapotrzebowania.

Po ustawieniu pola **Dodaj obliczone opóźnienie do opcji daty zapotrzebowania** na wartość **tak**, aby dodać opóźnienia do wymagań, system będzie uwzględniał zdolności produkcyjne zasobów i tworzył wykonalne zamówienia planowane. Ponowne obliczenie dat zamówień planowanych wydłuża czas pracy planowania głównego. W związku z tym, jeśli nie ma potrzeby używania opóźnień, należy określić opcje jako **nie**.

## <a name="positive-and-negative-days"></a>Dni dodatnie i ujemne

Dni dodatnie i ujemne wpływają na sposób, w jaki planowanie główne proponuje planowane zamówienia i akcje. W grupie zapotrzebowania na towar są ustawiane dni dodatnie i ujemne. Istnieje możliwość zdefiniowania różnych grup zapotrzebowania i ustawienia ich parametrów na stronie **grupy zapotrzebowania** (**Planowanie główne \> Ustawienia \> Zapotrzebowanie \> Grupy zapotrzebowania**).

### <a name="positive-days"></a>Ilość dni z dodatnim stanem magazynu

Liczba dni z dodatnim stanem magazynu wskazuje, jak daleko w przyszłości planowanie główne bierze pod uwagę bieżące zapasy lub pokwitowania, które zaspokoją przyszłe zapotrzebowanie. Jeśli na przykład liczba dni dodatnich jest ustawiona na **100**, bieżący zapas może zostać użyty do zrealizowania popytu w ciągu następnych 100 dni. Jeśli istnieje zamówienie 150 dni od daty bieżącej, planowanie główne utworzy zamówienie planowane w celu zaspokojenia tego zapotrzebowania, nawet jeśli dostępne zapasy towaru mogą być zgodne z zamówieniem. W przypadku szybkozbywalnych towarów, które mają krótki czas realizacji, może nie być konieczne użycie dostępnych zapasów w zamówieniu, które jest daleko w przyszłości. W tym przypadku szybko dostępne zapasy zostaną szybko usunięte i więcej zamówień można umieścić w przyszłości, aby zrealizować przyszłe zapotrzebowanie na czas, co byłoby możliwe z powodu krótkiego czasu realizacji towaru.

Liczba dni dodatnia wpływa również na komunikaty akcji. Na przykład system może zalecać zwiększenie planowanego zamówienia zakupu w celu uwzględnienia popytu w liczbie dni dodatnich w przyszłości. Jeśli liczba dni dodatnich jest ustawiona na **100** i jeśli istnieje zapotrzebowanie na dany towar w ciągu 30 dni od daty bieżącej, system utworzy zamówienie planowane w celu zaspokojenia tego zapotrzebowania. Jeśli dla tego samego towaru w ciągu 90 dni od daty bieżącej istnieje zapotrzebowanie, system zaleci zwiększenie ilości zamówienia w ciągu 30 dni od daty bieżącej, aby zamówienie obejmowało również zapotrzebowanie za 90 dni. Jeśli jednak w ciągu 150 dni od daty bieżącej istnieje zapotrzebowanie na towar, system nie zaleca zwiększenia ilości już zaplanowanego zamówienia. Zamiast tego zostanie utworzone nowe planowane zamówienie.

Z reguły liczba dni dodatnich jest ustawiona na liczbę z przedziału od najdłuższego czasu realizacji dla towarów i horyzontu czasowego zapotrzebowania. Zaleca się, aby towary, które są regularnie kupowane lub produkowane, były przypisywane do grupy zapotrzebowania, w której dni dodatnie są równe czasowi realizacji danego towaru.

### <a name="negative-days"></a>Ilość dni z ujemnym stanem magazynu

Dni ujemne wskazują, jak akceptowanego będą opóźnione pokwitowania towarów. Reprezentują one liczbę dni, po upływie których użytkownik chce zamówić nowe uzupełnienie zapasów w przypadku ujemnego stanu zapasów. Liczba dni ujemnych odpowiada na pytanie, czy zostanie utworzone nowe zamówienie zakupu dla towaru, czy raczej ma być używany istniejący zakup, nawet jeśli mamy pewność, że ten przedmiot będzie spóźniony.

Na przykład użytkownik ma zamówienie sprzedaży dla pozycji 15 dni od daty bieżącej. Istnieje także zamówienie zakupu dla tego samego towaru. To zamówienie zakupu zostanie odebrane w ciągu 20 dni od daty bieżącej. Czy chcesz, aby system utworzył zamówienie zakupu dla tego zamówienia sprzedaży, czy raczej chcesz użyć istniejącego zamówienia, mimo że nie możesz zrealizować zamówienia sprzedaży na czas? Jeśli liczba dni ujemnych jest ustawiona jako mniejsza niż **5** w celu wskazania, że towar może zostać opóźniony maksymalnie pięć dni, system utworzy nowe planowane zamówienie zakupu w celu zaspokojenia zamówienia sprzedaży. Jeśli liczba dni ujemnych jest większa niż **5**, system używa istniejącego zamówienia dla towaru.

Liczba dni ujemnych wpływa również na wydajność planowania głównego. Jeśli liczba dni ujemnych jest wysoka, wygenerowane zostanie wiele komunikatów akcji.

Zaleca się ustawienie liczby dni ujemnych na liczbę mniejszą niż czas realizacji towaru.

### <a name="dynamic-negative-days"></a>Dynamiczne dni ujemne

W dynamicznych dniach ujemnych należy uwzględnić czas realizacji towaru i już określone dni ujemne. System utworzy nowe planowane zamówienie zakupu na podstawie ujemnego horyzontu czasowego, który jest obliczany przy użyciu następującej formuły:

Czas realizacji + Dni ujemne + dzisiejsza data – wymagany termin

System używa tylko planowanych zamówień dostawy, które znajdują się w danym horyzoncie czasowym, i tworzy nowe zamówienie planowane poza nim. Zaletą dynamicznej liczby dni z ujemnym dniem jest to, że będzie on obejmował czas realizacji poszczególnych produktów, aby ponownie używać istniejących zamówień i uniknąć tworzenia nowych zamówień planowanych, które będą się kończyć na późniejszy dzień, z powodu opóźnień spowodowanych przez czas realizacji. 

Aby uzyskać więcej informacji, przejszyj [Dni ujemne i dynamiczne dni ujemne](/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]