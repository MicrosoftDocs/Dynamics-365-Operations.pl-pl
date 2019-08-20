---
title: Tworzenie planu dla oddziału
description: Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: daa185864052849b2c78d975a7eb02e9697cb618
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845184"
---
# <a name="create-a-plan-for-a-site"></a>Tworzenie planu dla oddziału

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

