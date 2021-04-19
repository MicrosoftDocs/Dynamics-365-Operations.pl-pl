---
title: Zarządzanie zmianami i szufladami kasowymi
description: W tym temacie wyjaśniono sposób konfigurowania i używania zmian w punkcie sprzedaży detalicznej (POS) Commerce.
author: jblucher
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailHardwareProfile, RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.custom: 105011
ms.assetid: 49a0fcc9-d4db-45ad-8c4b-213ccaced82b
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9d6fa36d7bb45e1cd9f8c3fbc1e60ac521f1f9b0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795460"
---
# <a name="shift-and-cash-drawer-management"></a>Zarządzanie zmianami i szufladami kasowymi

[!include [banner](includes/banner.md)]

W tym temacie wyjaśniono sposób konfigurowania i używania zmian w punkcie sprzedaży detalicznej (POS) Commerce.

W programie Dynamics 365 Commerce termin *zmiana* opisuje zbiór danych transakcyjnych i działań w puncie sprzedaży między dwoma punktami w czasie. Dla każdej zmiany oczekiwana kwota pieniędzy jest porównywana z kwotą podliczoną i zadeklarowaną.

Zazwyczaj zmiany są otwierane na początku dnia roboczego. W tym momencie użytkownik deklaruje kwotę początkową znajdującą się w szufladzie kasowej. Następnie w ciągu dnia są wykonywane transakcje sprzedaży. Na koniec dnia stan szuflady jest podliczany, a kwoty zamknięcia są deklarowane. Zmiana jest zamykana i następuje wygenerowanie końcowego raportu sprzedaży. Końcowy raport sprzedaży wskazuje, czy wystąpił nadmiar lub niedobór.

## <a name="typical-shift-scenarios"></a>Typowe scenariusze zmian

Aplikacja Commerce zawiera szereg opcji konfiguracji i operacji punktu sprzedaży, które wspierają obsługę wielu procesów biznesowych wykonywanych na koniec dnia w punkcie sprzedaży. W tym rozdziale opisano kilka typowych scenariuszy zmian.

### <a name="fixed-till"></a>Stały wkład szuflady kasowej

Dawniej ten scenariusz był używany najczęściej. Nadal jest dość powszechny. Na zmianie ze „stałym wkładem szuflady kasowej” zmiana i wkład szuflady są skojarzone z konkretną kasą. Nie są przenoszone między kasami. Zmiana ze „stałym wkładem szuflady kasowej” może być wykorzystywana przez jednego użytkownika lub współużytkowana przez wielu użytkowników. Zmiana ze „stałym wkładem szuflady kasowej” nie wymaga żadnej specjalnej konfiguracji.

### <a name="floating-till"></a>Ruchomy wkład szuflady kasowej

W zmianie z „ruchomym wkładem szuflady kasowej” zmianę i wkład szuflady można przenosić z jednej kasy do drugiej. Co prawda w kasie może istnieć tylko jedna aktywna zmiana dla każdej szuflady kasowej, ale zmiany można zawieszać, a następnie wznawiać później lub w innych kasach.

Na przykład w sklepie istnieją dwie kasy. Każda kasa jest otwierana na początku dnia, gdy kasjer zaczyna nową zmianę i wprowadza kwotę początkową. Gdy któryś kasjer jest gotowy do wzięcia przerwy, zawiesza swoją zmianę i wyjmuje wkład z szuflady kasowej. Wtedy ta kasa staje się dostępna dla innych kasjerów. Inny kasjer może się zalogować i otworzyć swoją zmianę na kasie. Kiedy pierwszemu kasjerowi skończy się przerwa, może on wznowić swoją zmianę, gdy tylko jedna z pozostałych kas stanie się dostępna. Zmiana z „ruchomym wkładem szuflady kasowej” nie wymaga żadnej specjalnej konfiguracji ani uprawnienia.

### <a name="single-user"></a>Jeden użytkownik

Wielu sprzedawców detalicznych woli pozwalać tylko na jednego użytkownika na każdej zmianie, tak aby zapewnić najwyższy poziom odpowiedzialności za gotówkę w szufladzie kasowej. Jeśli tylko jeden użytkownik może używać wkładu szuflady skojarzonego ze zmianą, można go pociągać do całkowitej odpowiedzialności za wszelkie rozbieżności. Jeśli więcej niż jeden użytkownik pracuje na danej zmianie, trudno jest określić, kto popełnił błąd lub kto próbuje kraść z wkładu szuflady kasowej.

### <a name="multiple-users"></a>Wielu użytkowników

Niektórzy sprzedawcy detaliczni są skłonni poświęcić jednoznaczną odpowiedzialność towarzyszącą zmianom z jednym użytkownikiem i zezwolić na więcej niż jednego użytkownika na zmianie. Takie podejście jest typowe w sytuacjach, gdy liczba użytkowników przekracza liczbę dostępnych kas, a potrzeba elastyczności i szybkości jest ważniejsza niż ryzyko straty. Jest również typowe w sytuacjach, gdy kierownicy sklepów nie mają własnych zmian, ale w razie potrzeby mogą korzystać ze zmian swoich dowolnych kasjerów. Aby się zalogować i korzystać ze zmiany, która została otwarta przez innego użytkownika, użytkownik musi mieć uprawnienie **Zezwalaj na wielokrotne logowanie do zmiany** w aplikacji POS.

### <a name="shared-shift"></a>Zmiana wspólna

Konfiguracja ze „zmianą wspólną” pozwala sprzedawcom detalicznym rozciągnąć jedną zmianę na wiele kas, szuflad kasowych i użytkowników. Zmiana wspólna ma jedną kwotę początkową i jedną kwotę zamknięcia, kóre są sumowane dla wszystkich szuflad kasowych. Zmiany wspólne stosuje się najczęściej w przypadku korzystania z urządzeń przenośnych. W tym scenariuszu dla kas nie są rezerwowane osobne szuflady kasowe. Zamiast tego wszystkie kasy mogą współużytkować jedną szufladę kasową.

Aby zmian wspólnych można było używać w sklepie, szuflada kasowa musi być skonfigurowana jako „Wspólna szuflada dla zmiany” w ustawieniu **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile sprzętu \> Szuflada**. Ponadto użytkownicy muszą mieć co najmniej jedno uprawnienie wobec wspólnej zmiany (Zezwalaj na zarządzanie zmianą udostępnioną i/lub Zezwalaj na używanie zmiany udostępnionej).

> [!NOTE]
> W każdym sklepie może być otwarta jednocześnie tylko jedna wspólna zmiana. W tym samym sklepie można używać zmian wspólnych i autonomicznych.

## <a name="shift-and-drawer-operations"></a>Operacje na zmianach i szufladach kasowych

Można wykonywać różne operacje w celu zmiany stanu zmiany albo zwiększenia lub zmniejszenia kwoty pieniędzy w szufladzie kasowej. W tej sekcji omówiono te operacje na zmianach dostępne w aplikacjach Modern POS i Cloud POS.

### <a name="open-shift"></a>Otwarta zmiana

Aplikacja POS wymaga, aby użytkownicy chcący wykonywać operacje skutkujące transakcją finansową, takie jak sprzedaż, zwrot lub zamówienie odbiorcy, mieli aktywne, otwarte zmiany.

Gdy użytkownik loguje się w aplikacji POS, system najpierw sprawdza, czy dla tego użytkownika jest dostępna aktywna zmiana w bieżącej kasie. Jeśli nie, użytkownik może otworzyć nową zmianę, wznowić istniejącą zmianę lub zalogować się w trybie „bez użycia szuflady”, w zależności od konfiguracji systemu i posiadanych uprawnień.

### <a name="declare-start-amount"></a>Zadeklaruj kwotę początkową

Ta operacja jest często pierwszą operacją wykonywaną na nowo otwartej zmianie. W tej operacji użytkownicy określają początkową kwotę pieniędzy w szufladzie kasowej na zmianie. Ta operacja jest ważna, ponieważ kwota początkowa przy obliczaniu nadmiaru/niedoboru na zakończenie zmiany jest brana pod uwagę.

### <a name="float-entry"></a>Pozycja zmiennoprzecinkowa

*Przyjęcia do kasy* są transakcjami niesprzedażowymi wykonywanymi podczas aktywnej zmiany, które zwiększają kwotę gotówki w szufladzie. Typowym przykładem przyjęcia do kasy byłaby transakcja wsypania drobnych do szuflady, gdy zaczyna ich brakować.

### <a name="tender-removal"></a>Pobranie środków płatniczych

*Pobrania środków płatniczych* są transakcjami niesprzedażowymi wykonywanymi podczas aktywnej zmiany, które zmniejszają kwotę gotówki w szufladzie kasowej. Ta operacja jest najczęściej stosowana w połączeniu z operacją przyjęcia do kasy na innej zmianie. Na przykład w kasie 1 kończą się drobne, więc użytkownik kasy 2 wykonuje pobranie środków płatniczych zmniejszające kwotę w jego szufladzie. Następnie użytkownik w kasie 1 wykonuje przyjęcie do kasy w celu zwiększenia kwoty w jego szufladzie kasowej.

### <a name="suspend-shift"></a>Zawieszenie zmiany

Użytkownicy mogą zawieszać swoje aktywne zmiany, aby zwolnić bieżącą kasę dla innego użytkownika, lub przenosić swoje do innych kas (taka zmiana jest często nazywana zmianą z „ruchomym wkładem szuflady kasowej”).

Zawieszenie zmiany uniemożliwia dokonywanie nowych transakcji i modyfikacji na zmianie do czasu, aż zmiana zostanie wznowiona.

### <a name="resume-shift"></a>Wznów zmianę

Ta operacja pozwala użytkownikom wznowić uprzednio zawieszoną zmianę na dowolnej kasie, która nie ma jeszcze aktywnej zmiany.

### <a name="tender-declaration"></a>Deklaracja środków płatniczych

Tę operację wykonuje się specjalnie w celu określenia łącznej kwoty pieniędzy znajdującej się obecnie w szufladzie kasowej. Użytkownicy najczęściej wykonują tę operację przed zamknięciem zmiany. Podana kwota jest porównywana z oczekiwaną kwotą ze zmiany w celu obliczenia kwoty nadwyżki/niedoboru.

### <a name="safe-drop"></a>Przekazanie pieniędzy do sejfu

Przekazania pieniędzy do sejfu można wykonywać na aktywnej zmianie w dowolnych momentach. Ta operacja powoduje usunięcie pieniędzy z szuflady kasowej w celu ich przeniesienia w bezpieczniejsze miejsce, takie jak sejf na zapleczu. Łączna kwota zarejestrowana dla przekazań pieniędzy do kasy jest uwzględniana w sumach dla zmiany, ale nie musi być włączana do deklaracji środków płatniczych.

### <a name="bank-drop"></a>Przekazanie pieniędzy do banku

Podobnie jak przekazania pieniędzy do sejfu, przekazania pieniędzy do banku są wykonywane na aktywnych zmianach. Ta operacja powoduje usunięcie pieniędzy ze zmiany w celu ich przygotowania do wpłaty do banku.

### <a name="blind-close-shift"></a>Zmiana z ukryciem raportu podczas zamknięcia kasy

*Zmiany z ukryciem raportu podczas zamknięcia kasy* nie są już aktywne, ale nie zostały jeszcze całkowicie zamknięte. W przeciwieństwie do zmian zawieszonych zmiany z ukryciem raportu podczas zamknięcia kasy nie mogą być wznawiane. Jednak operacje takie jak Deklaracja kwoty początkowej i Deklaracja środków płatniczych można na nich wykonać później lub z innej kasy.

Zmiany z ukryciem raportu podczas zamknięcia kasy są często używane w celu zwolnienia kasy dla nowego użytkownika lub zmiany bez konieczności uprzedniej pełnej inwentaryzacji, uzgadniania ani zamykania obecnej zmiany.

### <a name="close-shift"></a>Zamknięcie zmiany

Ta operacja obejmuje obliczenie sum dla zmiany i kwot nadwyżki/niedoboru, a następnie sfinalizowanie zmiany aktywnej lub zmiany z ukryciem raportu podczas zamknięcia kasy. W zależności od uprawnień użytkownika na zmianie może być również drukowany końcowy raport sprzedaży. Zamkniętych zmian nie można wznawiać ani modyfikować.

### <a name="print-x"></a>Drukuj częściowy raport sprzedaży

Ta operacja powoduje generowanie i drukowanie częściowego raportu sprzedaży dla obecnie aktywnej zmiany.

### <a name="reprint-z"></a>Ponowne drukowanie raportu końcowego

Ta operacja powoduje ponowne wydrukowanie ostatniego końcowego raportu, który został wygenerowany przez system po zamknięciu zmiany.

### <a name="manage-shifts"></a>Zarządzaj zmianami

Ta operacja pozwala użytkownikom wyświetlić wszystkie zmiany aktywne, zawieszone i zmiany z ukryciem raportu podczas zamknięcia kasy istniejące w sklepie. W zależności od posiadanych uprawnień użytkownicy mogą wykonywać końcowe procedury zamknięcia, takie jak operacje Deklaracja środków płatniczych i Zamknięcie zmiany, dla zmian z ukryciem raportu podczas zamknięcia kasy. Ta operacja pozwala również użytkownikom wyświetlać i usuwać nieprawidłowe zmiany w tych rzadkich przypadkach, gdzie zmiany pozostają w błędnym stanie po przełączeniu między trybami offline i online. Te nieprawidłowe zmiany nie zawierają żadnych informacji finansowych ani danych transakcyjnych wymaganych do uzgodnienia.

## <a name="shift-and-drawer-permissions"></a>Uprawnienia wobec zmian i szuflad kasowych

Poniższe uprawnienia w aplikacji POS decydują o tym, co użytkownik może, a czego nie może robić w różnych scenariuszach:

- **Zezwalaj na ukrycie raportu podczas zamknięcia kasy**
- **Zezwalaj na drukowanie częściowego raportu sprzedaży**
- **Zezwalaj na drukowanie końcowego raportu sprzedaży**
- **Zezwalaj na deklarację środków płatniczych**
- **Zezwalaj na deklarację obrotu kasowego**
- **Otwórz szufladę bez sprzedaży**
- **Zezwalaj na wielokrotne logowanie do zmiany** — To uprawnienie pozwala użytkownikowi logować się i korzystać ze zmiany, która została otwarta przez innego użytkownika. Użytkownicy, którzy nie mają tego uprawnienia, mogą się logować i korzystać tylko te zmian, które sami otworzyli.
- **Zezwalaj na zarządzanie zmianą udostępnioną** — Użytkownicy muszą mieć to uprawnienie, aby otworzyć lub zamknąć wspólną zmianę.
- **Zezwalaj na zarządzanie zmianą udostępnioną** — Użytkownicy muszą mieć to uprawnienie, aby się zalogować i wykorzystywać wspólną zmianę.

## <a name="back-office-end-of-day-considerations"></a>Uwagi dotyczące zakończenia dnia w systemach zaplecza

Sposób działania funkcji uzgadniania zmian i szuflad kasowych w aplikacji POS różni się od sposobu sumowania danych transakcji podczas obliczania zestawienia. Rozumienie tej różnicy jest bardzo ważne. W zależności od konfiguracji i stosowanych procesów biznesowych dane ze zmian w aplikacji POS (końcowy raport sprzedaży) mogą dawać inne wyniki, niż zestawienie obliczone w systemach zaplecza. Ta różnica nie musi oznaczać, że dane ze zmian lub obliczone zestawienie są błędne lub że występuje problem z danymi. Oznacza jedynie, że podane parametry mogą obejmować dodatkowe transakcje lub mniejszą liczbę transakcji albo że transakcje zostały zsumowane inaczej.

Chociaż każdy sprzedawca detaliczny ma różne wymagania biznesowe, zalecamy skonfigurowanie systemu w następujący sposób, aby uniknąć sytuacji, w których występują tego typu różnice:

Wybierz kolejno opcje **Handel detaliczny i inny \> Kanały \> Sklepy \> Wszystkie sklepy sieci sprzedaży \> Zestawienie/zamknięcie**, a następnie dla każdego sklepu w polach **Metoda zestawienia** i **Metoda zamknięcia** ustaw wartość **Zmiana**.

Ta konfiguracja pozwala zagwarantować, że zestawienia tworzone w systemach zaplecza będą obejmowały te same transakcje, jak zawierane na zmianach w aplikacji POS, a dane będą sumowane według tej zmiany.

Aby uzyskać więcej informacji o metodach tworzenia zestawień i zamykania, zobacz [Konfiguracje sklepu dla zestawień sieci sprzedaży](https://docs.microsoft.com/dynamics365/unified-operations/retail/tasks/store-configurations-retail-statements).


[!INCLUDE[footer-include](../includes/footer-banner.md)]