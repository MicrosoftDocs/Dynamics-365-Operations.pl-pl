---
title: Przeprowadzanie inspekcji faktur i najważniejszych danych w module rozrachunków z dostawcami
description: Ten artykuł zawiera więcej informacji dotyczących wykonywania audytu faktur i najważniejszych danych w module rozrachunków z dostawcami.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4525534f906322c7fe4c232f0f6da5b308829087
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775223"
---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Wykonywanie audytu faktur i najważniejszych danych w module rozrachunków z dostawcami

[!include [banner](../../includes/banner.md)]

Po otrzymaniu od dostawcy faktury za towary lub usługi na zamówieniu zakupu w procesach biznesowych firmy może być wymagane, aby towary lub usługi zostały dostarczone przed zatwierdzeniem płatności za fakturę. Zanim rozpoczniesz, upewnij się, że wybrano klucz konfiguracji Uzgadnianie faktur. 

Na stronie **Parametry modułu rozrachunków** z dostawcami upewnij się, że zaznaczono opcję **Włącz weryfikację uzgadniania faktur**, w polu **Księguj fakturę z rozbieżnościami** zaznaczono opcję **Wymagaj zatwierdzania**, a pole **Zasady uzgadniania wierszy** ma wartość **Uzgadnianie trzyelementowe**.

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
