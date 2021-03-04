---
title: Odwróć księgowanie arkusza
description: W tym temacie opisano możliwości wystornowania załączników z listy transakcji na załączniku lub z arkuszy finansowych.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3244d857a9135249130672501f8b766ff9a0680
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4446808"
---
# <a name="reverse-journal-posting"></a>Odwróć księgowanie arkusza

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości Microsoft Dynamics 365 Finance, które pozwalają wycofać cały arkusz lub wycofać jeden lub więcej załączników z listy transakcji załącznika bez względu na ich pochodzenie. 

## <a name="reversing-journals"></a>Wycofywanie arkuszy

Wiersze arkusza można odwracać pojedynczo. W przypadku księgowania wstecznego arkusza można również wycofywać cały arkusz finansowy. Wycofywanie arkusza: 

- Umożliwia otwarcie arkusza finansowego i przefiltrowanie arkuszy w zaksięgowanych arkuszach.
- Wybierz menu **Wycofaj** w górnej części strony.
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy
- Wybierz opcję **Tak**, aby zastosować istniejące daty transakcji lub **Nie**, aby wprowadzić nową datę. W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.
- Jeśli wybrano opcję **Nie**, wprowadź datę transakcji dla wycofania. 
- Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania.
- Wybierz przycisk **Wycofaj**.

Transakcje zostaną wycofane. 

Jeśli załącznik zawiera więcej niż 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego. Wyniki wycofania można ocenić, przeglądając komentarze w zadaniu wsadowym. Wszystkie transakcje, których nie można wycofać, będą wyświetlane w historii zadań wsadowych.

Jeśli załącznik zawiera 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast. Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Wycofywanie załączników z listy transakcji na załączniku. 

Można także wycofać załączniki z **listy transakcji na załączniku** do wszystkich ksiąg. Ponadto można jednocześnie wycofać więcej niż jeden załącznik 

Aby wycofać jeden lub więcej załączników: 

- Wybierz menu **Wycofaj** w górnej części strony
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy.
- Wybierz opcję **Tak**, aby zastosować istniejące daty transakcji lub **Nie**, aby wprowadzić nową datę. W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji, aby ją wycofać.
- Jeśli wybrano opcję **Nie**, wprowadź datę transakcji dla wycofania. 
- Umożliwia wprowadzenie komentarza opisującego transakcję wycofania.
- Wybierz przycisk **Wycofaj**.

Transakcje zostaną wycofane. 

Jeśli jest więcej niż 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego. Wyniki wycofania można ocenić, przeglądając komentarze w zadaniu wsadowym. Wszystkie transakcje, których nie można wycofać, będą zapisane w historii zadań wsadowych.

Jeśli liczba wierszy załącznika wynosi 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast. Wyniki zostaną wyświetlone w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, wraz z powodem. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

Transakcje można wycofać tylko wtedy, gdy spełniają one reguły biznesowe w celu ich wycofania. Płatności dostawcy nie można wycofać przy użyciu funkcji opisanych w tym temacie. Płatności dostawcy należy wycofać, wykonując kroki opisane w [Cofanie płatności dla dostawcy](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]