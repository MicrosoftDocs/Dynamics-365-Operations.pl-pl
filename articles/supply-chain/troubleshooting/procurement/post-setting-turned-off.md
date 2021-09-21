---
title: Ustawienie Księgowanie obciążenia konta w księdze nie jest włączone
description: Ten problem występuje w przypadku zafakturowania zamówienia zakupu, jeśli opcja „Księgowanie obciążenia konta w księdze” jest włączona na karcie „Faktura” na stronie „Parametry rozrachunków z dostawcami”
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 592444958dad4624fdc9098dc58df0a2e49e63de
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477328"
---
# <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Ustawienie Księgowanie obciążenia konta w księdze nie jest włączone

## <a name="symptoms"></a>Objawy

Ten problem występuje w przypadku zafakturowania zamówienia zakupu, jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**.

## <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
1. Na karcie **Faktura** ustaw opcję **Księgowanie obciążenia konta w księdze** na wartość *Tak*.
1. Przejdź do **Zarządzanie zapasami \> Konfiguracja \> Księgowanie \> Księgowanie**.
1. Na karcie **Zamówienie zakupu** upewnij się, że usunięto wszystkie wiersze wydatków zakupu produktu.
1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Zamówienia zakupu \> Wszystkie zamówienia zakupu**.
1. Umożliwia tworzenie zamówienia zakupu. W polu **Konto dostawcy** wybierz *1001 materiały biurowe Acme*.
1. Dodaj wiersz zamówienia zakupu z następującymi ustawieniami:

    - **Numer pozycji:** *D0011 projektor laserowy*
    - **Oddział:** *1*
    - **Magazyn:** *11*
    - **Ilość:** *4*

1. W okienku akcji na karcie **Zakup** w grupie **Akcja** wybierz opcję **Potwierdź**.
1. W okienku akcji na karcie **Odbierz** w grupie **Generowanie** wybierz pozycję **Przyjęcie produktu**.
1. W oknie dialogowym **Księgowanie dokumentu przyjęcia produktów** w polu **Dokument przyjęcia produktów** wprowadź dowolny numer, a następnie kliknij przycisk **OK**.
1. W okienku akcji na karcie **Faktura** w grupie **Generuj** wybierz **Faktura**.
1. W polu **Numer** wprowadź dowolną liczbę jako numer faktury.
1. Zaktualizuj stan uzgadniania i zaksięguj.
1. Zauważ, że teraz pojawia się następujący błąd podczas generowania faktury z zamówienia zakupu: „Numer konta dla typu transakcji Wydatki na zakup produktu nie istnieją”.

## <a name="resolution"></a>Rozwiązanie

Zależy to od ustawień parametrów dla faktur i grup faktur. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu na blogu: [Uwzględnianie opłaty za zakup i zmiany stanu zapasów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).
