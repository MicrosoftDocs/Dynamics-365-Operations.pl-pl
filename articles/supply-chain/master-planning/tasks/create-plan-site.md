---
title: Tworzenie planu dla oddziału
description: Planista produkcji oblicza zapotrzebowanie na materiały i zdolności produkcyjne do wytworzenia określonego towaru.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqTransPOUrgentFormPart, SysQueryForm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8330fc15074eb59762dac73d0b176bd7faadc
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469513"
---
# <a name="create-a-plan-for-a-site"></a>Tworzenie planu dla oddziału

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]