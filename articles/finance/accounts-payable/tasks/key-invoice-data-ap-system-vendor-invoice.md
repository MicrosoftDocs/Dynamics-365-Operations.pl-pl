---
title: Wpisywanie danych faktury w systemie AP za pomocą faktury od dostawcy
description: Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7abae6d680d899a0294ad3c298a4b0264ba01d0b
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189437"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a>Wpisywanie danych faktury w systemie AP za pomocą faktury od dostawcy

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ten przewodnik zadania pomoże utworzyć fakturę od dostawcy na podstawie zamówienia zakupu oraz wyświetlić wyniki uzgadniania zamówienia zakupu, przyjęcia i faktury (uzgadnianie trzyelementowe).


## <a name="create-a-purchase-order"></a>Tworzenie zamówienia zakupu
1. W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Wszystkie zamówienia zakupu**.
2. Kliknij przycisk **Nowy**.
3. W polu **Konto dostawcy** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
4. Znajdź dostawcę do wybrania. Na przykład przewiń w dół do dostawcy US-104.
5. Wybierz dostawcę US-104.
6. Kliknij przycisk **OK**.
7. W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Wybierz pozycję magazynową. Na przykład zaznacz numer towaru 1000.
9. Rozwiń skróconą kartę **Szczegóły wiersza**.
10. Kliknij kartę **Ustawienia**. Można ręcznie zastąpić zasady uzgadniania i określić nieużywanie uzgadniania, używanie uzgadniania dwuelementowego lub używanie uzgadniania trzyelementowego.  
11. W okienku akcji kliknij pozycję **Zakup.**
12. Kliknij przycisk **Potwierdź**.

## <a name="receive-the-products"></a>Odbieranie produktów
1. W okienku akcji kliknij pozycję **Odbierz.**
2. Kliknij opcję **Dokument przyjęcia produktów.**
3. W polu **Dokument przyjęcia** produktów wprowadź numer dokumentu przyjęcia produktów. Na przykład wpisz PR123.
4. Kliknij przycisk **OK**, aby zaksięgować dokument przyjęcia produktów.
5. Zamknij stronę.

## <a name="create-a-vendor-invoice"></a>Tworzenie faktury od dostawcy
1. W okienku nawigacji wybierz kolejno **Moduły > Rozrachunki z dostawcami > Zamówienia zakupu > Niezafakturowane zamówienia zakupu o stanie Otrzymano**.
2. Zaznacz utworzone przez siebie zamówienie zakupu.
3. W okienku akcji kliknij pozycję **Faktura**.
4. Kliknij opcję **Faktura**.
5. W polu **Numer** wprowadź numer faktury.
6. Wypełnij pole **Opis faktury**.
7. W polu **Data faktury** wprowadź datę.
8. W polu **Cena jednostkowa** wpisz 1200.
9. Kliknij przycisk **Dodaj wiersz.**
10. W polu **Numer towaru** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
11. Na liście znajdź numer towaru opłaty instalacyjnej. Na przykład S0001.
12. Zaznacz numer towaru opłaty instalacyjnej. Zwróć uwagę, że po wprowadzeniu zmian nie wykonano uzgadniania.  
13. Kliknij przycisk **Aktualizuj stan uzgadniania**.
14. W okienku akcji kliknij pozycję **Przegląd**.
15. Kliknij przycisk **Szczegóły uzgadniania**. Nowy wiersz z usługami nie musi być uzgadniany, dlatego pozostaje stan „Nie wykonano”.  
16. Zaznacz dokument przyjęcia produktów dla otrzymanej pozycji magazynowej. Wiersz z dokumentem przyjęcia produktów został uzgodniony, ale występuje niezgodność ilości lub ceny, dlatego operacja kończy się niepowodzeniem.  
17. W polu **Cena jednostkowa** wpisz liczbę. Teraz, gdy cena jednostkowa jest zgodna, stan został zaktualizowany na Powodzenie. Jeśli zasady pozwalają na rozbieżności lub gdy uzgadnianie jest traktowane jedynie jako ostrzeżenie, można zaksięgować fakturę.  
18. Zamknij stronę.
19. Kliknij przycisk **Księguj**.
20. Zamknij formularz. Zwróć uwagę, że zamówienie zakupu nie jest już wyświetlane jako otrzymane, ale niezafakturowane.  
