---
title: Wykonywanie audytu faktur i najważniejszych danych w systemie rozrachunków z dostawcami
description: Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e1af0dac107be6009eb3ca576c49ac5abbd9848
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139951"
---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Wykonywanie audytu faktur i najważniejszych danych w systemie rozrachunków z dostawcami

[!include [banner](../../includes/banner.md)]

Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. 

Na stronie Parametry modułu rozrachunków z dostawcami upewnij się, że zaznaczono opcję Włącz weryfikację uzgadniania faktur, w polu Księguj fakturę z rozbieżnościami zaznaczono opcję Wymagaj zatwierdzania, a pole Zasady uzgadniania wierszy ma wartość Uzgadnianie trzyelementowe.

Ta procedura wykorzystuje firmę demonstracyjną USMF. Czynności te wykonuje menedżer ds. rozrachunków z dostawcami lub menedżer księgowości.


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. Przejdź do okna **Wszystkie zamówienia zakupu.**
2. Kliknij przycisk **Nowy**.
3. W polu **Konto dostawcy** wpisz wartość.
4. Kliknij przycisk **OK**.
5. Kliknij przycisk **Dodaj wiersz.**
6. W polu **Numer towaru** wpisz wartość.
7. W okienku akcji kliknij pozycję **Zakup.**
8. Kliknij przycisk **Potwierdź**.

## <a name="post-a-product-receipt"></a>Księgowanie dokumentu przyjęcia produktów
1. W okienku akcji kliknij pozycję **Odbierz.**
2. Kliknij opcję **Dokument przyjęcia produktów.**
3. W polu **Dokument przyjęcia produktów** wpisz wartość.
4. Kliknij przycisk **OK**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Rejestrowanie i uzgadnianie faktury od dostawcy z dokumentem przyjęcia produktów
1. W okienku akcji kliknij pozycję **Faktura > Faktura**.
2. W polu **Numer** wpisz wartość.
3. Na liście **Domyślnie z zaznacz opcję Zamówiona ilość**, aby otworzyć rozwijane okno dialogowe.
4. W polu **Domyślna ilość dla wierszy** zaznacz opcję.
5. Kliknij przycisk **OK**.
6. Kliknij przycisk **Tak**.
7. Kliknij opcję **Dopasuj dokumenty przyjęcia produktów**.
8. Kliknij przycisk **OK**.
9. W okienku akcji kliknij pozycję **Przegląd**.
10. Kliknij przycisk **Szczegóły uzgadniania**.

