---
title: Rozwiązywanie problemów dotyczących kompilowania i przesyłania ładunku
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z tworzeniem ładunków i wysyłkami w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0c82ec33eb2f1d918b86770343f41e3b9d0996a52ecb5ee091c0576c33770f31
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756686"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Rozwiązywanie problemów dotyczących kompilowania i przesyłania ładunku

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z tworzeniem ładunków i wysyłkami w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Otrzymuję następujący komunikat o błędzie: „Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe...”

### <a name="issue-description"></a>Opis problemu

Podczas próby zwolnienia zwrotu zamówienia sprzedaży do magazynu jest wyświetlany następujący komunikat o błędzie:

> Nie można utworzyć wiersza ładowania dla tego wiersza zamówienia, ponieważ zawiera on wymiary magazynowe, które są nieprawidłowe. Nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru lokalizacji w hierarchii rezerwacji. Usuń nieprawidłowe wymiary z wiersza zamówienia.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Niestety, produkt nie obsługuje przetwarzania ładunku dla procesu zwrotu sprzedaży. Nie można więc zwolnić zwrotu zamówienia sprzedaży do magazynu.

W transakcjach zamówienia sprzedaży nie można odwoływać się do wymiarów magazynowych, które znajdują się poniżej wymiaru **Lokalizacji** w hierarchii rezerwacji. Rozwiązanie polega na usunięciu nieprawidłowych wymiarów z wiersza zamówienia.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Pojawia się następujący komunikat o błędzie: „Jeden z wierszy jest już w ładunku. Zwolnienie do magazynu jest niemożliwe".

### <a name="issue-description"></a>Opis problemu

W przypadku ręcznego tworzenia ładunków lub konfigurowania procesu w taki sposób, aby ładunki były już tworzone przed wprowadzeniem wiersza zamówienia sprzedaży, założeniem jest, że kolejna wersja zostanie wykonana ręcznie i zostanie użyta trasa i ocena z ładunku.

W innym możliwym scenariuszu podejmowana jest próba automatycznego wydania do magazynu, ale nie udało się utworzyć pracy w procesie grupy czynności. W związku z tym zostanie utworzona otwarta wysyłka lub ładunek. Ta otwarta przesyłka lub ładunek blokuje następnie kolejne próby automatycznego zwolnienia zamówienia do czasu usunięcia otwartej przesyłki lub załadowania albo ręcznego ponownego przetworzenia grupy czynności.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Można zwolnić ze strony zamówienia sprzedaży lub automatyczne zwolnienie można wykonać ze strony zwolnienia zamówienia sprzedaży tylko wtedy, gdy przed wydaniem do magazynu nie ma żadnego ładunku. Ładunek zostanie automatycznie utworzony po przetworzeniu grupy czynności.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Pojawia się następujący komunikat o błędzie: „Nie można przetworzyć korekty dokumentu dostawy. Dokument dostawy zawiera tylko pozycje, które podlegają procesom zarządzania magazynem, ponieważ nie są one obsługiwane przez korektę dokumentu dostawy".

### <a name="issue-description"></a>Opis problemu

Po zaksięgowaniu dokumentu dostawy nie można go anulować, ponieważ przycisk **Anuluj** jest niedostępny. Nie można również poprawić dokumentu dostawy. W przypadku próby pojawi się ten komunikat o błędzie.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Aby skorygować zaksięgowane dokumenty dostawy dla towarów, dla których włączono funkcję zaawansowanego zarządzania magazynem (WMS), należy wykonać księgowanie z ładunku, a nie bezpośrednio w zamówieniu.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Jak można utworzyć pracę z ładunków wychodzących zamiast grup czynności?

### <a name="issue-description"></a>Opis problemu

Oto jeden ze sposobów odtworzenia tego problemu.

1. Utwórz ładunek wychodzący, używając zamówienia sprzedaży lub zlecenia przeniesienia.
2. Zwalnianie ładunku do magazynu.
3. Zauważ, że żadne prace pobrania nie zostały jeszcze wygenerowane.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Jeśli praca musi zostać wygenerowana natychmiast po zwolnieniu ładunku, należy odpowiednio skonfigurować szablon grupy czynności. W szablonie grupy czynności ustaw następujące opcje na *Tak*:

- Automatyczne tworzenie grupy czynności
- Przetwarza grupę czynności w czasie uwalniania jej do magazynu
- Automatyczne uwolnienie grupy czynności

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Nie mogę ponownie zwolnić częściowo wysłanego ładunku.

### <a name="issue-description"></a>Opis problemu

Nie można zwolnić częściowo wysłanego ładunku do magazynu. Po wydaniu do magazynu pojawia się komunikat „Operacja zakończona”, ale nic się nie dzieje i nie jest tworzona praca dla pozostałej ilości. Ten problem występuje, gdy używasz funkcji transportu ładunku i istnieje niekompletna rezerwacja.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

[KB problem 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) („Częściowo wysłane ładunki można ponownie pogrupować w grupy czynności i ponownie przetworzyć”) został naprawiony w [wydaniu 10.0.15](../get-started/whats-new-scm-10-0-15.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]