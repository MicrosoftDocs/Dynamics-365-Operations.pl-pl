---
title: "Zarządzanie zapasami w sklepie"
description: "W tym artykule opisano typy dokumentów, których można używać do zarządzania zapasami."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: 37f9cb7d8118c3aa4cf287a8b7ed2dc9270acb52
ms.contentlocale: pl-pl
ms.lasthandoff: 04/26/2017


---

# <a name="manage-store-inventory"></a>Zarządzanie zapasami w sklepie

[!include[banner](includes/banner.md)]


W tym artykule opisano typy dokumentów, których można używać do zarządzania zapasami.

Następujące typy dokumentów służą do zarządzania zapasami w organizacji.

## <a name="purchase-orders"></a>Zamówienia zakupu
Zamówienia zakupu są tworzone w centrali. Jeśli magazyn sprzedaży detalicznej znajduje się w nagłówku zamówienia zakupu, zamówienia można otrzymać w sklepie przy użyciu aplikacji Modern POS (MPOS) lub Cloud POS dostępnej w module Microsoft Dynamics 365 for Operations — Handel detaliczny. Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować. Można też zatwierdzić ilości i wysłać do centrali. Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Operations w polu **Dostarczone teraz** na zamówieniu zakupu.

## <a name="transfer-orders"></a>Zamówienia przeniesienia
W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, z której można wysyłać towary. W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie pobrania w aplikacji MPOS lub Cloud POS. Po pobraniu żądanych ilości zostaną one zatwierdzone i przesłane do centrali. Zlokalizowane w centrali ilości, które zostały pobrane w sklepie, są wyświetlane w programie Dynamics 365 for Operations w polu **Wyślij teraz** na zamówieniu przeniesienia. W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, do której można wysyłać towary. W takim przypadku zamówienie przeniesienia jest wyświetlane w sklepie jako żądanie przyjęcia w aplikacji MPOS lub Cloud POS. Po wprowadzeniu ilości, które są odbierane w sklepie, można je zapisać lokalnie i modyfikować. Można też zatwierdzić ilości i wysłać do centrali. Zlokalizowane w centrali ilości, które zostały odebrane w sklepie, są wyświetlane w programie Dynamics 365 for Operations w polu **Dostarczone teraz** na zamówieniu przeniesienia.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji
Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji. Centrala tworzy dokument inwentaryzacji, który można otrzymać w sklepie. Rzeczywista ilość dostępnych zapasów jest wprowadzana w aplikacji MPOS lub Cloud POS. Niezaplanowane inwentaryzacje są inicjowane w sklepie, a rzeczywista ilość dostępnych zapasów jest aktualizowana w aplikacji MPOS lub Cloud POS. W odróżnieniu od zaplanowanej inwentaryzacji niezaplanowana nie ma wstępnie zdefiniowanej listy pozycji. Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali. W centrali dane podlegają sprawdzeniu i zaksięgowaniu.






