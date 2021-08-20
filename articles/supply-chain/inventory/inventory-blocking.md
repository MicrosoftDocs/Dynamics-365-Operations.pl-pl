---
title: Blokowanie zapasów
description: Ten artykuł zawiera omówienie mechanizmu blokowania zapasów, który jest częścią procesu kontroli jakości w Supply Chain Management. Używając blokowania, można zapobiec przetwarzaniu i zużywaniu zapasów.
author: perlynne
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 58dd5c5b3d7b2f077305fa4d420fc55702acbe7ebba049ae9ac78a1362ff2523
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770295"
---
# <a name="inventory-blocking"></a>Blokowanie zapasów

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera omówienie mechanizmu blokowania zapasów, który jest częścią procesu kontroli jakości w Supply Chain Management. Używając blokowania, można zapobiec przetwarzaniu i zużywaniu zapasów.

Pozycje magazynowe można blokować w następujący sposób:

- Ręcznie
- Tworząc zlecenie kontroli jakości
- Za pomocą procesu, który generuje zlecenia kontroli jakości
- przez blokowanie stanu zapasów

## <a name="blocking-items-manually"></a>ręczne blokując towary

Ilość towaru można zablokować przez utworzenie transakcji na stronie **Blokowanie zapasów**. Ręcznie można zablokować jedynie pozycje dostępne na stanie w magazynie. Dla ilości zablokowanych ręcznie należy rozważyć, czy oczekiwane przychody powinny znajdować się w działaniach planowania jako oczekiwana ilość zapasów na stanie. Oczekiwane przyjęcia to zablokowane towary, które według przewidywań po inspekcji będą dostępne jako zapasy na stanie. Można zachować oczekiwaną datę. Domyślnie opcja **Oczekiwane przyjęcia** jest zaznaczona dla towarów, które są zablokowane za pomocą zlecenia kontroli jakości. Można anulować blokowanie ilości ręcznie blokowanych przez usunięcie transakcji na stronie **Blokowanie zapasów**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blokując towary poprzez tworzenie zlecenia kontroli jakości

Można określić elementy, które muszą być skontrolowane, przez utworzenie zlecenia kontroli jakości na stronie **zleceń kontroli jakości**. Po utworzeniu zlecenia kontroli jakości, określona ilość towaru jest zablokowana. Plan pobierania próbek skojarzony ze zleceniem kontroli jakości kontroluje ilość towaru, który ma być sprawdzany, nie ilość, która jest zablokowana. Niezależnie od ilości, która zostanie wysłana do inspekcji, jak określono w planie pobierania próbek, ilość towaru wprowadzona w zleceniu kontroli jakości jest ilością, która zostaje zablokowana.

> [!NOTE]
> W planowaniu głównym nie są obsługiwane zarówno funkcje daty ważności partii, jak i blokowania stanu magazynowego. Może to spowodować podwójne wykluczenie dostępnych zapasów, co może nastąpić podczas planowania głównego. Zaleca się, aby zamiast stanu zapasów zablokowanie przeterminowanych partii było uzależnione od kodów dyspozycji partii.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blokując towary za pomocą procesu, który generuje zlecenia kontroli jakości.

Jeśli w procesie kontroli jakości określono konieczność kontroli pozycji, ilość towaru zostanie automatycznie zablokowana. Tak więc podczas automatycznego generowania zlecenia kontroli jakości plan próbkowania towaru skojarzony z zamówieniem kontroli jakości określa ilość towarów, która jest zablokowana i ilość towarów, które mają zostać sprawdzone. W przypadku zaznaczenia opcji **Pełne blokowanie** na stronie **Kontrola wyrywkowa towarów**, całkowita ilość, na przykład, w wierszu zamówienia zakupu jest zablokowana podczas inspekcji, niezależnie od ilości kontroli wyrywkowej towarów.

### <a name="example"></a>Przykład

W poniższym przykładzie generowane jest zlecenie kontroli jakości podczas księgowania dokumentu dostawy zamówienia zakupu. Na stronie **Powiązania jakości** określono, że księgowanie dokumentu dostawy zamówienia zakupu jest określone jako proces, który aktywuje zlecenia kontroli jakości.

|Ustawienia |Akcja użytkownika |Wynik |
|----|---|---|
| Skojarzenie jakości określa, że przy księgowaniu dokumentu dostawy zamówienia zakupu musi zostać wygenerowane zlecenie kontroli jakości. Ustawienia kontroli wyrywkowej towarów zlecenia kontroli jakości określa, że musi zostać skontrolowane 10% ilości w wierszu zamówienia zakupu. Co więcej, przy zaznaczonym polu wyboru **Pełne blokowanie** ustawienie pobierania próbek wskazuje, że podczas inspekcji, niezależnie od ilości, która zostanie wysłana do inspekcji, należy zablokować pełną ilość w wierszu zamówienia zakupu. | Dokumentu dostawy zostaje zaksięgowany. | Zlecenie kontroli jakości zostało wygenerowane. 10% ilości towaru w zamówieniu zakupu jest wysyłane do inspekcji. Całkowita ilość wiersza zamówienia zakupu jest zablokowana. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>przez blokowanie towarów za pomocą blokowania stanu magazynu

Można określić, które stany zapasów powodują blokowanie, za pomocą parametru **Blokowania zapasów** na stronie **Stany zapasów**. Stanów zapasów nie można używać jako stanów blokowania dla zleceń produkcyjnych, zamówień sprzedaży, zamówień przeniesienia, transakcji wychodzących i integracji projektu. W przypadku pracy wychodzącej należy użyć towarów z dostępnym stanem zapasów. Jeśli masz towary o stanie **uszkodzone** i zostało dla nich uruchomione planowanie główne, pozycje te zostaną uznane za brakujące, a zapasy są uzupełniane automatycznie.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Zachowaj ostrożność podczas blokowania elementów, które korzystają zarówno z blokowania stanu zapasów, jak i blokowania zleceń jakości

Można utworzyć zlecenie kontroli jakości skojarzone z zapasami, dla których jest włączony stan zapasów z włączonym parametrem **Blokowania zapasów**. W takim przypadku zlecenie kontroli jakości spowoduje wygenerowanie dodatkowego rekordu blokowania zapasów oprócz rekordu utworzonego przez stan zapasów. Blokowanie zapasów dla zlecenia kontroli jakości będzie mieć włączony parametr **Oczekiwane przyjęcia**, co wygeneruje dodatkową *Zamówioną transakcję* magazynową, która jest także zablokowana przez jej stan zapasów. Ta kombinacja może prowadzić do trudności w zrozumieniu znaczenia wygenerowanych transakcji magazynowych, ponieważ będzie wyglądać tak, jakby całkowita ilość zablokowana przekraczała całkowitą ilość w magazynie. Przeanalizujmy transakcje na przykładzie przyjęcia 10 sztuk towaru A0001 ze zleceniem kontroli jakości wygenerowanym dla próbki 1 sztuki. To działanie będzie również zależało od tego, czy na stronie **Parametry zarządzania zapasami i magazynem** jest włączona opcja **Rezerwuj zamówione towary**.

>[!NOTE]
>Jeśli razem jest przy użyciu blokowania stanu zapasów i zleceń kontroli jakości, zdecydowanie zaleca się, aby włączyć opcję **Rezerwuj zamówione towary**.

### <a name="example-with-reserve-ordered-items-enabled"></a>Przykład z włączoną opcją „Zarezerwuj zamówione produkty”

Po włączeniu opcji **Rezerwuj zamówione towary** wszystkie transakcje blokowania zapasów będą mieć stan *Zarezerwowane fizycznie* lub *Zamówione zarezerwowane*.

| Odwołanie do transakcji magazynowej | Pokwitowanie | Wystawienie | Ilość | Oddział | Magazyn | Stan zapasów | Lokalizacja | Numer identyfikacyjny | Komentarz |
|---|---|---|---|---|---|---|---|---|---|
| Zamówienie zakupu | Zakupione | | 10 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | | 
| Blokowanie zapasów | | Fizycznie zarezerwowane | -9 szt. | 2 | 24 | Blokowanie | | | Transakcja wygenerowana przez blokowanie stanu zapasów |
| Blokowanie zapasów | | Fizycznie zarezerwowane | -1 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | Transakcja wygenerowana przez blokowanie kontroli wyrywkowej zlecenia kontroli jakości |
| Blokowanie zapasów | Zamówiona | | 1 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | Oczekiwane wpływy z blokowania wyrywkowej kontroli jakości |
| Blokowanie zapasów | | Zamówione zarezerwowane | 1 szt. | 2 | 24 | Blokowanie | | | Transakcja wygenerowana przez blokowanie stanu zapasów

### <a name="example-with-reserve-ordered-items-disabled"></a>Przykład z wyłączoną opcją „Zarezerwuj zamówione produkty”

Jeśli opcja **Zarezerwuj zamówione produkty** są wyłączone, nie można zarezerwować oczekiwanych przychodów, ponieważ mają stan *Zamówione*, więc niektóre elementy blokowania zostaną zablokowane w stanie *Na zamówienie*.

| Odwołanie do transakcji magazynowej | Pokwitowanie | Wystawienie | Ilość | Oddział | Magazyn | Stan zapasów | Lokalizacja | Numer identyfikacyjny | Komentarz |
|---|---|---|---|---|---|---|---|---|---|
| Zamówienie zakupu | Zakupione | | 10 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | |
| Blokowanie zapasów | | Fizycznie zarezerwowane | -9 szt. | 2 | 24 | Blokowanie | | | Transakcja wygenerowana przez blokowanie stanu zapasów |
| Blokowanie zapasów | | Fizycznie zarezerwowane | -1 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | Transakcja wygenerowana przez blokowanie kontroli wyrywkowej zlecenia kontroli jakości |
| Blokowanie zapasów | Zamówiona | | 1 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | Oczekiwane wpływy z blokowania wyrywkowej kontroli jakości |
| Blokowanie zapasów | | Zamówione | 1 szt. | 2 | 24 | Blokowanie | RECV | receiptLp1 | Transakcja wygenerowana przez blokowanie stanu zapasów

Należy zwrócić uwagę na różnicę między stanem transakcji a wymiarami między tymi dwoma sprawami. Z tego powodu zaleca się włączenie opcji **Zarezerwuj zamówione produkty**.

<!-- KFM: (Enable this section when the feature leaves private preview)

### Disable expected receipts from quality orders that sample blocked inventory feature

To simplify the inventory transactions in the case of quality orders that sample inventory blocked as a consequence of inventory status, the system provides a feature that disables expected receipts from such quality orders. As the expected receipt is in any case immediately blocked by inventory status blocking, there is no reduction of on-hand inventory because of this change.

-->

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie i obsługa blokowania zapasów](tasks/create-maintain-inventory-blocking.md)

[Procesy zarządzania jakością](quality-management-processes.md)

[Sprawdzenie jakości towarów](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]