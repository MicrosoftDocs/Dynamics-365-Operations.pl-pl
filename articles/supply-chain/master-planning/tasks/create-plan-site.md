--- 
title: "Tworzenie planu dla oddziału"
description: "Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru."
author: YuyuScheller
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1452c5d6f5dd8d0dd4cb08eb5cc9a48fd8f875f9
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-plan-for-a-site"></a>Tworzenie planu dla oddziału

[!include[task guide banner](../../includes/task-guide-banner.md)]

Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru. Po utworzeniu propozycji źródeł zaopatrzenia wyszukuje zamówienia w oddziale, dla którego wykonuje planowanie, i je akceptuje (potwierdza), począwszy od najpilniejszych. Najpilniejszymi zamówieniami są te, które trzeba zaakceptować w bieżącym dniu. Wykonaj te zadania przy użyciu danych firmy demonstracyjnej USMF.


## <a name="create-a-materials-and-capacity-plan-for-an-item"></a>Tworzenie planu materiałów i zdolności produkcyjnych dla towaru
1. Kliknij opcję Planowanie główne.
    * Należy przejść do domyślnego pulpitu nawigacyjnego.  
2. Kliknij przycisk Uruchom.
3. Rozwiń sekcję Rekordy do uwzględnienia.
4. Kliknij przycisk Filtr.
5. Na liście oznacz wybrany wiersz.
6. W polu Kryteria wpisz wartość.
    * Przykład: D0001  
7. Kliknij przycisk OK.
8. Kliknij przycisk OK.
    * Może to potrwać kilka minut.  
9. Odśwież stronę.

## <a name="identify-the-urgent-planned-orders-for-the-item"></a>Identyfikowanie pilnych zamówień planowanych na towar
1. Otwórz filtr kolumny Numer towaru.
2. Zastosuj filtr w polu „Numer towaru” o wartości „D0001” i użyj operatora filtru „zaczyna się od”.
3. Otwórz filtr kolumny Data zamówienia.
4. Zastosuj filtr do pola „Data zamówienia” z wartością bieżącej daty i operatorem „równa się”.

## <a name="firm-all-the-urgent-orders-for-the-item"></a>Akceptowanie wszystkich pilnych zamówień na towar
1. Na liście oznacz wszystkie wiersze lub usuń ich oznaczenie.
2. Kliknij przycisk Akceptuj.
3. Kliknij przycisk OK.


