---
title: Rozlicz resztę
description: Można rozliczyć kwotę pozostałą z działania rozliczenia przez zastosowanie tej kwoty do konta księgowego.
author: mikefalkner
manager: aolson
ms.date: 10/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 14244ccfef69a8bff3390539ff7b851a8f5b5ec1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009575"
---
# <a name="settle-remainder"></a>Rozlicz resztę

[!include [banner](../includes/banner.md)]

Można rozliczyć kwotę pozostałą z działania rozliczenia przez zastosowanie tej kwoty do konta księgowego lub innego klienta. Można rozliczyć pozostałą kwotę, gdy rozliczane są kwoty wprowadzane do arkusza lub gdy rozliczane są tylko otwarte transakcje.

## <a name="setting-up-defaults"></a>Konfigurowanie wartości domyślnych 
Należy włączyć funkcję rozliczania reszty i ustawić wartości domyślną przed użyciem funkcji rozliczania reszty

1)  Kliknij **Rozrachunki z odbiorcami > Parametry > Rozliczenia** lub **Rozrachunki z dostawcami > Parametry > Rozliczenia**
2)  Wybierz kartę **Rozliczenia** i kliknij przycisk **Włącz rozliczanie reszty**
3)  W **Domyślnym kodzie przyczyny** wybierz domyślny kod przyczyny. Kody przyczyny musi być już skonfigurowany w **Rozrachunki z odbiorcami > Ustawienia > Kody przyczyn odpisów odbiorcy** lub **Rozrachunki z dostawcami > Ustawienia > Kody przyczyn odpisów odbiorcy**. **Domyślne konto rozliczania reszty** będzie domyślnym kontem przypisanym do kodu przyczyny odpisu.
3)  W razie potrzeby zaktualizuj **Domyślne konto rozliczania reszty**.
4)  W **Domyślna nazwa arkusza** wybierz arkusz płatności, który zostanie użyty, jeśli chcesz utworzyć dziennik płatności, gdy rozliczasz tylko otwarte transakcje. Jeśli włączysz funkcję rozliczania reszty, musisz dodać domyślną nazwę arkusza.

## <a name="settle-remainder-from-a-journal"></a>Rozliczanie reszty z arkusza
Jeśli nie zostanie włączona funkcja **Rozliczanie reszty**, można nadal wprowadzać transakcję w arkuszu, a następnie rozliczyć transakcje zgodnie z tym arkuszem tak jak w przeszłości. Po kliknięciu przycisku **OK** otwarte saldo na fakturze jest pomniejszane o kwotę środków pieniężnych. Jeśli dostępne środki pieniężne na pokrywają kwoty faktury, pozostaje ona otwarta z pozostałą kwotą do rozliczenia w późniejszym czasie.

Gdy funkcja **Rozliczanie reszty** jest włączona, można rozliczyć resztę na koncie księgowym. Można także przenieść resztę na konto innego odbiorcy (dla transakcji z odbiorcami) lub innego dostawcy (dla transakcji z dostawcami) zamiast pozostawiania otwartych faktur. 

Aby rozliczyć resztę ze strony **Rozliczenie** wykonaj następujące kroki:

1)  Na stronie **Rozliczenia** zaznacz faktury lub transakcje, które chcesz rozliczyć.
2)  Kliknij przycisk **Rozliczanie reszty**.
3)  W wyświetlonym oknie dialogowym widoczna będzie kwota to rozliczenia na koncie księgowym, data, która zostanie użyta do rozliczenia kwoty, domyślny kod przyczyny z parametrów oraz domyślne konto z parametrów. 
4)  Jeśli chcesz zmienić domyślną przyczynę, należy wybrać nową przyczynę rozliczenia. Konto rozliczeniowe zmieni się na konto skojarzone z kodem przyczyny.
5)  Edytuj konto rozliczeniowe, jeśli chcesz je zmienić.
6)  W przypadku rozliczania transakcji odbiorcy i jeśli chcesz, aby reszta była przeniesiona na innego odbiorcę, wybierz odbiorcę w sekcji **Rozlicz resztę względem konta odbiorcy**. W przypadku rozliczania transakcji dostawcy i jeśli chcesz, aby reszta była przeniesiona na innego dostawcę, wybierz dostawcę w sekcji **Rozlicz resztę względem konta dostawcy**.
6)  Kliknij **Rozliczanie reszty**.
7)  Zostanie wyświetlona strona **Arkusz**. Dodatkowy wiersz zostanie dodany do arkusza z kwotą reszty do rozliczenia jako kwotą i kontem rozliczenia reszta jako kontem przeciwstawnym. Po dodaniu odbiorcy lub dostawcy w taki sposób, aby możliwe było przeniesienie kwoty rozliczenia na innego dostawcę lub odbiorcę, w arkuszu pojawi się nowy wiersz pozwalający przenieść kwotę rozliczenia na tego odbiorce lub dostawcę.

Po zaksięgowaniu arkusza, otwarta transakcja zostanie w pełni rozliczona. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Rozliczanie reszty tylko w kontekście rozliczania otwartych transakcji
Można również rozliczyć resztę w przypadku rozliczania otwartych transakcji bez arkusza.

Aby rozliczyć resztę, należy wykonać następujące czynności:

1)  Na stronie **Rozliczenia** zaznacz faktury lub transakcje, które chcesz rozliczyć.
2)  Kliknij **Rozliczanie reszty**.
3)  W wyświetlonym oknie dialogowym widoczna będzie kwota to rozliczenia na koncie księgowym, data, która zostanie użyta do rozliczenia kwoty, domyślny kod przyczyny z parametrów oraz domyślne konto z parametrów. 
4)  Jeśli chcesz zmienić domyślną przyczynę, należy wybrać nową przyczynę rozliczenia. Konto rozliczeniowe zmieni się na konto skojarzone z kodem przyczyny.
5)  Edytuj **konto rozliczeniowe**, jeśli chcesz je zmienić.
6)  W przypadku rozliczania transakcji odbiorcy i jeśli chcesz, aby reszta była przeniesiona na innego odbiorcę, wybierz odbiorcę w sekcji **Rozlicz resztę względem konta odbiorcy**. W przypadku rozliczania transakcji dostawcy i jeśli chcesz, aby reszta była przeniesiona na innego dostawcę, wybierz dostawcę w sekcji **Rozlicz resztę względem konta dostawcy**.
7)  Istnieje również możliwość utworzenia arkusza płatności z rozliczeniem reszty lub tylko zaksięgowania bez arkusza. Wybierz **Tak** dla **Edytuj w arkuszu**, aby utworzyć arkusz płatności. Można edytować utworzony arkusz płatności.
8)  Kliknij **Rozliczanie reszty**. Jeśli wybrano opcję utworzenia arkusza, przycisk zmieni się na **Utwórz arkusz**. Kliknij zamiast tego **Utwórz arkusz**.
9)  Jeśli utworzono arkusz płatności, strony arkusza zostanie otwarta po kliknięciu przycisku **Rozlicz resztę**. Wiersz zostanie dodany do arkusza z kwotą reszty do rozliczenia jako kwotą i kontem rozliczenia reszta jako kontem przeciwstawnym. Po dodaniu odbiorcy lub dostawcy w taki sposób, aby możliwe było przeniesienie kwoty rozliczenia na innego dostawcę lub odbiorcę, w arkuszu pojawi się nowy wiersz pozwalający przenieść kwotę rozliczenia na tego odbiorce lub dostawcę.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]