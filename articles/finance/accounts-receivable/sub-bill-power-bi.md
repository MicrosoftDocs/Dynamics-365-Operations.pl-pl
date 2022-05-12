---
title: Rozliczanie subskrypcji treści Power BI
description: W tym temacie opisano, co wchodzi w skład zawartości rozliczania subskrypcji Microsoft Power BI.
author: JodiChristiansen
ms.date: 04/13/2022
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-04-13
ms.openlocfilehash: fad96bdaf60e7772e9ea1ff937435b0274303505
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645424"
---
# <a name="subscription-billing-power-bi-content"></a>Rozliczanie subskrypcji treści Power BI

[!include[banner](../includes/banner.md)]

W tym temacie opisano, co wchodzi w skład zawartości rozliczania subskrypcji Microsoft Power BI. Wyjaśniono, jak uzyskać dostęp do raportów programu Power BI, oraz zamieszczono informacje o modelu danych i jednostkach użytych do zbudowania pakietu. 

## <a name="overview"></a>Omówienie

Materiały Power BI dotyczące rozliczania subskrypcji zostały stworzone z myślą o pracownikach i menedżerach zajmujących się rozliczaniem subskrypcji. Dostarcza kluczowych wskaźników rozliczeniowych subskrypcji, takich jak miesięczne powtarzające się przychody (MRR) dla harmonogramów rozliczeniowych oraz informacje o saldzie malejącym i wodospadach dla harmonogramów odroczeń. Wykorzystuje ona dane z list rozliczeniowych i list odroczeń, aby zapewnić przegląd powtarzających się dochodów i przychodów.

Zawartość Power BI składa się z następujących trzech zakładek, które zawierają łącznie cztery raporty analityczne: 

- **Analytics – MRR** - Ta zakładka zawiera raport **Miesięcznych rozliczeń cyklicznych** oraz raport **Szczegóły harmonogramu rozliczeń**.
- **Analizy – Wykres kaskadowy** – Ta zakładka zawiera raport **Wykres kaskadowy przychodów**.
- **Analityka – Saldo malejące** – ta zakładka zawiera raport **Saldo malejące**.

## <a name="view-data-on-the-analytical-reports"></a>Przeglądaj dane na raportach analitycznych

Zanim będziesz mógł przeglądać dane na raportach analitycznych, musisz uruchomić okresowy proces, który wygeneruje dane raportowe dla każdego raportu. Te dane, których wymagają raporty, muszą być wygenerowane, ponieważ nie są przechowywane bezpośrednio w bazie danych. 

1. Przejdź do **Podskrypcja billingowa \> Cykliczne rozliczanie kontraktów \> Zadania okresowe \> Przetwarzanie wsadowe raportów analitycznych MRR** i wykonaj poniższe kroki:

    1. Wprowadź zakres dat nie dłuższy niż trzy lata.
    2. Opcjonalnie: Skonfiguruj powtarzające się zadanie procesu wsadowego, aby okresowo odświeżać dane.
    3. Kliknij przycisk **OK**.

2. Po zakończeniu działania zadania wsadowego przejdź do **Administracji systemu \> Konfiguracji \> Sklep encji** i odśwież pomiar zbiorczy **Raportu MRR**. 
3. Przejdź do **Rozliczanie subskrypcji \> Odraczanie przychodów i kosztów \> Zadania okresowe \> Wykres kaskadowy – przetwarzanie wsadowe raportów analitycznych MRR** i wykonaj poniższe kroki:

    1. Wprowadź datę początkową i datę końcową, które obejmują nie więcej niż 26 okresów. 
    2. Jeśli chcesz, aby przewidywane kwoty z poprzednich okresów były widoczne w bieżącym okresie, ustaw opcję **Przewidywanie kwot z przeszłości w bieżącym okresie** na **Tak**.
    3. Opcjonalnie: Skonfiguruj powtarzające się zadanie procesu wsadowego, aby okresowo odświeżać dane.
    4. Kliknij przycisk **OK**. 

4. Po zakończeniu działania zadania wsadowego przejdź do **Administracji systemu \> Konfiguracji \> Sklep encji** i odśwież pomiar zbiorczy **Raport: wykres kaskadowy**.
5. Przejdź do **Rozliczanie subskrypcji \> Odraczanie przychodów i kosztów \> Zadania okresowe \> Zmniejszające się saldo – przetwarzanie wsadowe raportów analitycznych MRR** i wykonaj poniższe kroki:

    1. Wprowadź datę początkową i datę końcową, które obejmują nie więcej niż 26 okresów. 
    2. Jeśli chcesz, aby przewidywane kwoty z poprzednich okresów były widoczne w bieżącym okresie, ustaw opcję **Przewidywanie kwot z przeszłości w bieżącym okresie** na **Tak**.
    3. Opcjonalnie: Skonfiguruj powtarzające się zadanie procesu wsadowego, aby okresowo odświeżać dane.
    4. Kliknij przycisk **OK**.

6. Po zakończeniu działania zadania wsadowego przejdź do **Administracji systemu \> Konfiguracji \> Sklep encji** i odśwież pomiar zbiorczy **Raport o malejącym saldzie**.

## <a name="accessing-the-power-bi-content"></a>Przechodzenie do pakietu zawartości usługi Power BI

Zawartość rozliczeń subskrypcji w Power BI jest widoczna w obszarze roboczym **Rozliczenia subskrypcji**.
