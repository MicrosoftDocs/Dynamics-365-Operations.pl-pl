---
title: "Rejestrator zadań i Pomoc dla punktu sprzedaży"
description: "W tym temacie opisano, jak korzystać z Rejestratora zadań w programach Retail Modern POS (MPOS) i Cloud POS."
author: mugunthanm
manager: AnnBe
ms.date: 06/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 1205393
ms.assetid: 2f13e9cf-55b5-458b-8c32-3f8cd98c9ecf
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: e66208ccceb4c248c2704bb7358d77447e032205
ms.openlocfilehash: 43360ea18ccc0fc4622f6da70ff10f2aca8b56c8
ms.contentlocale: pl-pl
ms.lasthandoff: 12/14/2017

---

# <a name="task-recorder-and-help-for-pos"></a>Rejestrator zadań i Pomoc dla punktu sprzedaży

W tym temacie opisano, jak korzystać z Rejestratora zadań w programach Retail Modern POS (MPOS) i Cloud POS.

<a name="overview"></a>Przegląd
--------

Rejestrator zadań w programie Retail Modern POS lub Cloud POS jest to nowe rozwiązanie, utworzone z myślą o krótkim czasie reakcji. Zawiera elastyczny interfejs programowania aplikacji (API) umożliwiający rozszerzenie i bezproblemową integrację z użytkownikami zapisów procesu biznesowego. Ponadto integracja Rejestratora zadań z narzędziem do modelowania procesów biznesowych (BPM) w usługach Microsoft Dynamics Lifecycle Services ([https://bpm.lcs.dynamics.com](https://bpm.lcs.dynamics.com/)) została przyspieszona. W związku z tym użytkownicy mogą nadal tworzyć diagramy procesów biznesowych na podstawie zapisów w celu analizy i projektowania swoich zgłoszeń.

## <a name="architecture"></a>Architektura
Rejestrator zadań może rejestrować działania użytkownika na komputerze klienckim z precyzyjną dokładnością. Każdy element sterujący jest wyposażony w narzędzie do powiadamiania Rejestratora zadań o wykonaniu czynności przez użytkownika. Element sterujący powiadamia Rejestrator zadań o wystąpieniu zdarzenia i przekazuje wszelkie stosowne informacje o odpowiedniej akcji użytkownika w czasie rzeczywistym. Z tych informacji Rejestrator zadań uzyskuje dane o typie akcji użytkownika (na przykład kliknięciu przycisku, wprowadzeniu wartości lub nawigowaniu) oraz wszelkie dane związane z daną akcją użytkownika (na przykład wartość i typ danych wejściowych, kontekst formularza lub rekordu). Rejestrator zachowuje informacje z wystarczającą ilością szczegółów w celu zagwarantowania, że odtwarzanie nagrania może przeprowadzić zarejestrowane akcje dokładnie tak samo, jak były wykonywane przez użytkownika. (Funkcja odtwarzania nie została jeszcze zaimplementowana w programie Retail Modern POS lub Cloud POS.)

## <a name="basic-configuration"></a>Konfiguracja podstawowa
Aby włączyć rejestrowanie zadań w punkcie sprzedaży, wykonaj następujące kroki.

1.  Kliknij kolejno opcje **Handel detaliczny** &gt; **Ustawienia kanału** &gt; **Ustawienia punktu sprzedaży** &gt; **Rejestry**.
2.  Kliknij rejestr, aby włączyć rejestrowanie zadań.
3.  Na karcie **Rejestr**, na skróconej karcie **Ogólne** dla opcji **Włącz rejestrowanie zadań** wybierz ustawienie **Tak**.
4.  Kliknij przycisk **Zapisz**.
5.  Wybierz kolejno opcje **Handel detaliczny** &gt; **Dane IT sieci sprzedaży** &gt; **Harmonogram dystrybucji**.
6.  Wybierz zadanie **Rejestry (1090)**, a następnie kliknij przycisk **Uruchom teraz**.

## <a name="create-a-recording"></a>Utwórz nagranie
Wykonaj następujące kroki, aby utworzyć nowe nagranie przy użyciu Rejestratora zadań.

1.  Uruchom program Retail Modern POS lub Cloud POS i zaloguj się.
2.  Na stronie **Ustawienia**, w sekcji **Rejestrator zadań** kliknij przycisk **Otwórz rejestratora zadań**. Pojawi się okienko **Rejestrator zadań**. Przed rozpoczęciem nowego nagrania możesz kliknąć przycisk **Zamknij** (**X**) w prawym górnym rogu, aby zamknąć okienko **Rejestrator zadań**. Aby ponownie otworzyć okienko, powtórz krok 2.
[![okienko rejestratora zadań](./media/newrecording-1024x450.jpg)](./media/newrecording.jpg)

3.  Wprowadź nazwę i opis nagrania, a następnie kliknij przycisk **Uruchom**. Sesja nagrywania rozpoczyna się natychmiast po kliknięciu przycisku **Uruchom**.

**Uwaga:** po kliknięciu przycisku **Zamknij** (**X**) w prawym górnym rogu, gdy operacja rejestrowania jest w toku, okienko **Rejestrator zadań** zostaje zamknięte, ale sesja rejestrowania nie jest zakończona. Aby ponownie otworzyć okienko rejestratora zadań, kliknij przycisk **Pomoc** (znak zapytania) w górnej części ekranu. 

[![Znak zapytania](./media/help.jpg)](./media/help.jpg)

4.  Po kliknięciu przycisku **Uruchom** Rejestrator zadań wchodzi w tryb rejestrowania. W okienku **Rejestrator zadań** są wyświetlane informacje i elementy sterujące, które są związane z procesem rejestrowania.
5.  Wykonaj działania, które chcesz wykonać w interfejsu użytkownika (UI) Retail Modern POS lub Cloud POS.
6.  Aby zakończyć sesję rejestrowania, kliknij przycisk **Zatrzymaj**.

## <a name="download-options"></a>Opcje pobierania
Po zakończeniu sesji rejestrowania wyświetlanych jest kilka opcji, dzięki czemu można pobrać nagranie. 
[![Opcje pobierania](./media/downlaod-options.jpg)](./media/downlaod-options.jpg)

### <a name="save-to-this-pc"></a>Zapisz na tym komputerze

Pakiet rejestracji umożliwia odtwarzanie przewodnika po zadaniu, obsługę rejestrowania oraz edytowanie adnotacji do nagrania. (Funkcja ta nie została jeszcze zaimplementowana w programie Retail Modern POS i Cloud POS.)

### <a name="export-as-word-document"></a>Eksportuj jako dokument programu Word

Nagranie można zapisać jako dokument programu Microsoft Word. Dokument będzie zawierać nagrane kroki i wykonane zrzuty ekranu.

### <a name="save-as-developer-recording"></a>Zapisz jako nagranie dewelopera

Nieprzetworzony plik nagrania będzie przydatny w scenariuszach deweloperskich, takich jak generowanie kodu testowego. (Ta funkcja nie została jeszcze zaimplementowana.)

## <a name="recording-controls"></a>Elementy sterujące rejestrowania
### <a name="recording-controlsmediacontrolsjpgmediacontrolsjpg"></a>[![Elementy sterujące rejestrowania](./media/controls.jpg)](./media/controls.jpg)

### <a name="stop"></a>Zatrzymaj

Kliknij przycisk **Zatrzymaj**, aby zakończyć sesję rejestrowania. Pamiętaj, że nie można ponownie uruchomić sesji po jej zakończeniu. W związku z tym upewnij się, czy rejestrowanie zostało ukończone przed zakończeniem sesji.

### <a name="pause"></a>Wstrzymaj

Kliknij przycisk **Wstrzymaj**, aby tymczasowo zatrzymać (wstrzymać) sesję rejestrowania i kontynuować operację. Czynności wykonane po kliknięciu przycisku **Wstrzymaj** nie są rejestrowane.

### <a name="continue"></a>Kontynuuj

Aby wznowić sesję rejestrowania po wstrzymaniu jej, kliknij przycisk **Kontynuuj**.

### <a name="capture-screenshots"></a>Przechwyć zrzuty ekranu

Rejestrator zadań może przechwycić zrzuty ekranu interfejsu użytkownika Retail Modern POS podczas nagrywania procesu biznesowego. Aby włączyć funkcję przechwytywania zrzutów ekranu, należy dla opcji **Przechwyć zrzuty ekranu** wybrać ustawienie **Tak**, a następnie wykonać nagranie. Po zakończeniu nagrywania kliknij przycisk **Zatrzymaj** i pobierz dokument programu Word. Dokument będzie zawierał czynności w odpowiednimi zrzutami ekranu.

#### <a name="note"></a>Uwaga
> Funkcja przechwytywania zrzutów ekranu nie jest obsługiwana w programie Modern POS.

### <a name="start-task-and-end-task"></a>Rozpoczęcie i zakończenie zadania

Początek i koniec zestawu zgrupowanych kroków można określić przy użyciu przycisków **Rozpocznij zadanie** i **Zakończ** **zadanie**. Kliknij przycisk **Rozpocznij zadanie**, aby dodać krok rozpoczęcia zadania, a następnie wykonaj kroki, które powinny zostać uwzględnione w grupie. Po zakończeniu wykonywania kroków do uwzględnienia w grupie, kliknij przycisk **Zakończ zadanie**. Zadania pomagają porządkować procedury. Zadania można zagnieżdżać wewnątrz innych zadań. W ten sposób można lepiej organizować bardzo długie i złożone procesy biznesowe.

## <a name="adding-annotations"></a>Dodawanie adnotacji
Adnotacja to dodatkowy tekst, który można dodać do kroku w nagraniu. Na przykład można użyć adnotacji w celu udostępnienia użytkownikowi dodatkowego kontekstu lub instrukcji. Można dodać adnotacje, przed lub po kroku. Adnotację można dodać do dowolnego kroku, klikając przycisk **Edytuj** (symbol ołówka) po prawej stronie kroku. 

[![Przycisk Edytuj dla kroku](./media/annotate.jpg)](./media/annotate.jpg)

### <a name="texts-and-notes"></a>Teksty i notatki

Można użyć pól **Teksty** i **Notatki** w celu dodania tekstu, który ma być skojarzony z krokiem w przewodniku po zadaniu.
[![Pola Teksty i Notatki](./media/annotatesteps.jpg)](./media/annotatesteps.jpg)

#### <a name="text"></a>Tekst

Tekst wprowadzony w polu **Tekst** pojawi się *nad* tekstem kroku w przewodniku po zadaniu. Ta lokalizacja jest odpowiednia dla tekstu, który ma być odczytany przez użytkownika przed wykonaniem kroku.

#### <a name="notes"></a>Notatki

Tekst wprowadzony w polu **Notatki** pojawi się *pod* tekstem kroku w przewodniku po zadaniu. Aby odczytać tekst notatki, użytkownik musi rozwinąć tekst kroku w oknie podręcznym. Ta lokalizacja jest odpowiednia dla materiałów do przeczytania opcjonalnie lub innych informacji, która mogą być użyteczne dla użytkownika, ale nie są konieczne dla użytkownika do zakończenia akcji.

## <a name="help-in-retail-modern-pos-and-cloud-pos"></a>Pomoc w programie Retail Modern POS i Cloud POS
Aby wyświetlić własne niestandardowe nagrania zadań w okienku Pomocy programu Retail Modern POS i Cloud POS, by mogły być wyświetlane jako tekst, należy zapisać nagrania zadań w bibliotece BPM, a następnie zaktualizować parametry systemu Pomocy, aby wskazywał bibliotekę BPM. Aby uzyskać więcej informacji, zobacz [Łączenie z systemem Pomocy](../fin-and-ops/get-started/help-connect.md). Pomoc programu Retail Modern POS i Cloud POS wyszukuje usługi LCS w czasie rzeczywistym. Przeszukuje wszystkie biblioteki BPM wybrane w parametrach programu Microsoft Dynamics 365 for Retail — Pomoc i przedstawia odpowiednie wyniki. Aby uzyskać dostęp do menu **Pomoc**, kliknij przycisk **Pomoc** (znak zapytania) znajdujący się u góry ekranu, a następnie w polu wyszukiwania wpisz nazwę procesu i kliknij przycisk wyszukiwania. 

[![Przycisk Pomoc](./media/help.jpg)](./media/help.jpg) 

Po kliknięciu pozycji Przewodnik po zadaniu w wynikach wyszukiwania można wyświetlić kroki jako tematy pomocy lub wyeksportować kroki do dokumentu programu Word. 
#### <a name="note"></a>Uwaga
> Pomoc w programach Retail Modern POS and Cloud POS nie powoduje uruchamiania przewodników po zadaniach dopasowanych do otwartego formularza lub wykonywanej operacji. Należy wpisać nazwę procesu w polu wyszukiwania, a następnie kliknąć przycisk **Szukaj**.


