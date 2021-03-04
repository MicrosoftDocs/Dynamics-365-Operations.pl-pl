---
title: Rozwiązywanie problemów z pokwitowaniem produktów i fakturowaniem
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z pokwitowaniami produktów i fakturowaniem.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: a89effb686d60dde9d11f99be51d4101897ad4ea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4435648"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a>Rozwiązywanie problemów z pokwitowaniem produktów i fakturowaniem

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z pokwitowaniami produktów i fakturowaniem.

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a>Nie mogę zaksięgować więcej niż jednej faktury dla wiersza zamówienia zakupu zawierającego pozycje oparte na kategorii.

Ilość jest obowiązkowa, jeśli chcesz zaksięgować faktury. Dlatego jeśli zafakturowano całą ilość w wierszu tylko dla części kwoty, nie będzie można zafakturować pozostałej kwoty na innej fakturze.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>Otrzymuję komunikat o błędzie „Nie ustawiono odwołania do obiektu” podczas potwierdzania zamówienia zakupu lub podczas księgowania faktury od dostawcy zgłoszony został wyjątek „Obiekt docelowy wywołania” zgłosił wyjątek.

Ten problem może wystąpić z powodu niespójności w dystrybucji zamówień zakupu.

Aby odblokować ten wystawiony błąd i zresetować zamówienie zakupu do stanu *Wersji roboczej*, należy przejść do obszaru **Zaopatrzenie i sourcing \> Zadania okresowe \> Wyczyść \> Reset dystrybucji zamówienia zakupu**. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu w blogu: [Rozwiązywanie błędów dystrybucji zamówienia zakupu w Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu.

Nie można skonsolidować wielu dokumentów przyjęcia produktów w jednym zamówieniu zakupu, jeśli inne wiersze dokumentu przyjęcia produktów mają różne daty księgowania.

W starszych wersjach rozwiązania Microsoft Dynamics 365 Supply Chain Management konsolidacja była dopuszczalna w tej sytuacji. Jednak praktyka ta jest podatna na błędy. Data księgowania w tworzonych wierszach zamówienia zakupu nie powinna różnić się od daty księgowania w wierszach przyjęcia produktów, na podstawie których utworzono te wiersze zamówienia. (Data księgowania w wierszach zamówienia jest zgodna z datą księgowania w nagłówku zamówienia). Dlatego konsolidacja wielu przyjęć produktów w pojedyncze zamówienia zakupu nie jest już dozwolona.

Data księgowania jest używana na przykład w odniesieniu do rezerwacji budżetu i przyszłych zobowiązań wiążących. Dlatego należy go zachować podczas przejścia od przyjęcia produktu do zamówienia.

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a>W przypadku anulowania przyjęcia produktów transakcje mogą zostać zaksięgowane na zawieszonym koncie księgowym.

### <a name="issue-description"></a>Opis problemu

W przypadku anulowania przyjęcia produktów system umożliwia księgowanie transakcji na zawieszonych kontach księgowych, nawet jeśli konta główne są zawieszone.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

Poniższa procedura przedstawia jeden ze sposobów odtworzenia błędu.

1. Na stronie **Parametry rozrachunków z dostawcami** na karcie **Ogólne** upewnij się, że opcja **Księguj dokument przyjęcia produktów w księdze** jest ustawiona na wartość *Tak*.
1. Utwórz zamówienie zakupu i dodaj wiersz zamówienia z ilością *1 000* dla produktu.
1. Potwierdź zamówienie zakupu.
1. Zaksięguj dokument przyjęcia produktów i sprawdź załączniki.
1. Zawiesić odpowiednie konta główne, *200140* i *140200*.
1. Anuluj zaksięgowane przyjęcia produktu.
1. Zwróć uwagę, że transakcje mogą być księgowane na zawieszonych kontach księgowych.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Transakcje mogą być księgowane na zawieszonych kontach księgowych po anulowaniu przyjęcia produktów, ponieważ takie zachowanie umożliwia prawidłowe księgowanie.

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a>Numer kuponu przyjęcia produktu jest używany, nawet jeśli podczas przyjęcia produktu nie jest generowany żaden dowód finansowy.

Jeśli dla grupy modeli towaru dla opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** jest ustawiona wartość *Nie*, księgowanie nie będzie wykonywane w księdze głównej. Jednak zdarzenie fizyczne zostanie zarejestrowane do celów księgowania w księdze podrzędnej, a to zdarzenie wymaga numeru załącznika. Ten numer załącznika jest numerem załącznika, do którego istnieje odwołanie w transakcjach magazynowych.

Zaleca się ustawienie opcji **Naliczone zobowiązanie w dokumencie przyjęcia produktów** na wartość *Tak*, jak to opisano w następującym wpisie na blogu: [Księguj różne opłaty w momencie przyjęcia produktów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a>Ustawienie Księgowanie obciążenia konta w księdze nie jest włączone.

### <a name="issue-description"></a>Opis problemu

Ten problem występuje w przypadku zafakturowania zamówienia zakupu, jeśli opcja **Księgowanie obciążenia konta w księdze** ma wartość *Tak* na karcie **Faktura** na stronie **Parametry rozrachunków z dostawcami**.

### <a name="reproduce-the-issue"></a>Odtwórz ten błąd

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

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Zależy to od ustawień parametrów dla faktur i grup faktur. Aby uzyskać więcej informacji, zajrzyj do następującego wpisu na blogu: [Uwzględnianie opłaty za zakup i zmiany stanu zapasów](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]