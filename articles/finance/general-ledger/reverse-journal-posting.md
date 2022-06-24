---
title: Wycofywanie księgowania arkusza
description: W tym artykule opisano możliwości wystornowania załączników z listy transakcji na załączniku lub z arkuszy finansowych.
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bec7d5d0dd64a2d89b00e2aa630a4fe670feaa2b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868410"
---
# <a name="reverse-journal-posting"></a>Wycofywanie księgowania arkusza

[!include [banner](../includes/banner.md)]

W tym artykule opisano możliwości aplikacji Microsoft Dynamics 365 Finance, które pozwalają wycofać cały arkusz lub wycofać jeden lub więcej załączników z listy transakcji załącznika bez względu na ich pochodzenie. 

Aby można było skorzystać z dowolnej z funkcji opisanych w tym artykule, należy ją włączyć w systemie. Administratorzy mogą skorzystać z obszaru roboczego **Zarządzanie funkcjami**, aby sprawdzić stan funkcji i włączyć ją, jeśli istnieje taka potrzeba. Ta funkcja jest wymieniona w następujący sposób:
 - Moduł: Księga główna
 - Nazwa funkcji: **Masowe wycofania wielu dokumentów**

## <a name="reversing-journals"></a>Wycofywanie arkuszy

Wiersze arkusza można odwracać pojedynczo. W przypadku księgowania wstecznego arkusza można również wycofywać cały arkusz finansowy. Wycofywanie arkusza: 

- Przefiltruj według zaksięgowanych arkuszy i otwórz widok **Wiersze** w arkuszu.
- Wybierz menu **Wycofaj** w górnej części strony.
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy.
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

- Wybierz menu rozwijane **Wycofaj cały arkusz** w górnej części strony.
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy.
- Wybierz opcję **Tak**, aby zastosować istniejące daty transakcji lub **Nie**, aby wprowadzić nową datę. W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji, aby ją wycofać.
- Jeśli wybrano opcję **Nie**, wprowadź datę transakcji dla wycofania. 
- Umożliwia wprowadzenie komentarza opisującego transakcję wycofania.
- Wybierz przycisk **Wycofaj**.

Transakcje zostaną wycofane. 

Jeśli jest więcej niż 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego. Wyniki wycofania można ocenić, przeglądając komentarze w zadaniu wsadowym. Wszystkie transakcje, których nie można wycofać, będą zapisane w historii zadań wsadowych.

Jeśli liczba wierszy załącznika wynosi 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast. Wyniki zostaną wyświetlone w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, wraz z powodem. Kliknij przycisk **OK**, aby zamknąć okno dialogowe.

Transakcje można wycofać tylko wtedy, gdy spełniają one reguły biznesowe w celu ich wycofania. Płatności dostawcy nie można wycofać przy użyciu funkcji opisanych w tym artykule. Płatności dostawcy należy wycofać, wykonując kroki opisane w [Cofanie płatności dla dostawcy](../accounts-payable/reverse-vendor-payment.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
