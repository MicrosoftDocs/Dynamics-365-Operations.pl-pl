---
title: Odwróć księgowanie arkusza
description: W tym temacie opisano możliwości wystornowania załączników z listy transakcji na załączniku lub z arkuszy finansowych.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248592"
---
# <a name="reverse-journal-posting"></a>Odwróć księgowanie arkusza

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości Microsoft Dynamics 365 Finance, które pozwalają wycofać cały arkusz lub wycofać jeden lub więcej załączników z listy transakcji załącznika bez względu na ich pochodzenie. 

## <a name="reversing-journals"></a>Wycofywanie arkuszy

Wiersze arkusza można odwracać pojedynczo. W przypadku księgowania wstecznego arkusza można również wycofywać cały arkusz finansowy. Wycofywanie arkusza: 
- Umożliwia otwarcie arkusza finansowego i przefiltrowanie arkuszy w zaksięgowanych arkuszach
- W menu w górnej części strony kliknij Odwróć
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy
- Wybierz opcję tak, aby zastosować istniejące daty transakcji lub nie, aby wprowadzić nową datę. W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.
- Jeśli wybrano opcję nie, wprowadź datę transakcji dla wycofania. 
- Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania
- Kliknij przycisk wycofaj

Transakcje zostaną wycofane. 

Jeśli liczba wierszy załącznika przekracza 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego. Wyniki wycofania można przejrzeć, przeglądając komentarze w uruchomionym zadaniu wsadowym. Wszystkie błędy zostaną odnotowane w historii zadania wsadowego.

Jeśli liczba wierszy załącznika nie przekracza 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast. Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć. Kliknij przycisk OK, aby zamknąć okno dialogowe.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Wycofywanie załączników z listy transakcji na załączniku. 

Można także wycofać załączniki z **listy transakcji na załączniku** do wszystkich ksiąg. Ponadto można jednocześnie wycofać więcej niż jeden załącznik 

Aby wycofać jeden lub więcej załączników: 
- W menu w górnej części strony kliknij Odwróć
- Zostanie wyświetlona łączna liczba załączników i wierszy załączników oraz łączna kwota wycofywanych wierszy
- Wybierz opcję tak, aby zastosować istniejące daty transakcji lub nie, aby wprowadzić nową datę. W niektórych przypadkach okres oryginalnej transakcji może zostać zamknięty i konieczne jest wprowadzenie nowej daty transakcji dla wycofania.
- Jeśli wybrano opcję nie, wprowadź datę transakcji dla wycofania. 
- Umożliwia wprowadzenie komentarza, który ma zostać dodany do transakcji wycofania
- Kliknij przycisk wycofaj

Transakcje zostaną wycofane. 

Jeśli liczba wierszy załącznika przekracza 100 wierszy, proces wycofania zostanie uruchomiony przy użyciu procesu przetwarzania wsadowego. Wyniki wycofania można przejrzeć, przeglądając komentarze w uruchomionym zadaniu wsadowym. Wszystkie błędy zostaną odnotowane w historii zadania wsadowego.

Jeśli liczba wierszy załącznika nie przekracza 100 wierszy lub mniej, proces wycofywania zostanie uruchomiony natychmiast. Wyniki zostaną przedstawione w oknie dialogowym, w którym jest wyświetlany dowolny załącznik, którego nie można wycofać, oraz powód, dla którego nie można go cofnąć. Kliknij przycisk OK, aby zamknąć okno dialogowe.

