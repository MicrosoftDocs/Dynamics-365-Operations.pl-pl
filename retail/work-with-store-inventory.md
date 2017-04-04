---
title: "Zarządzanie zapasami w sklepie"
description: "W tym artykule opisano typy dokumentów, które służy do zarządzania zapasami."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Zarządzanie zapasami w sklepie

W tym artykule opisano typy dokumentów, które służy do zarządzania zapasami.

Następujące typy dokumentów służą do zarządzania zapasami w organizacji.

## <a name="purchase-orders"></a>Zamówienia zakupu
Zamówienia zakupu są tworzone w centrali. Jeśli magazyn sprzedaży detalicznej jest zawarty w nagłówku zamówienia zakupu, zamówienia mogą być odbierane w sklepie przy użyciu nowoczesnych POS (MPOS) lub POS chmury Microsoft Dynamics 365 dla operacji - sieci sprzedaży. Po wprowadzeniu ilości, które są odbierane w sklepie one mogą być zapisywane lokalnie dla żadnych dodatkowych modyfikacji. Można też zatwierdzić ilości i wysłać do centrali. W centrali, ilości, które zostały odebrane w sklepie są wyświetlane w usłudze Dynamics 365 dla operacji, w **odebrać** pola na zamówieniu zakupu.

## <a name="transfer-orders"></a>Zamówienia przeniesienia
W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, z której można wysyłać towary. W takim przypadku zamówienie przeniesienia pojawia się w sklepie jako żądanie pobrania w MPOS lub POS chmury. Po są zbierane ilości, które są wymagane, są zatwierdzone i wysyłane do centrali. W centrali, ilości, które zostały pobrane w sklepie są wyświetlane w usłudze Dynamics 365 dla operacji, w **Wyślij teraz** pola w zleceniu przesunięcia. W zleceniu przesunięcia można określić, że dany sklep jest lokalizacją, do której można wysyłać towary. W takim przypadku zamówienie przeniesienia pojawia się w sklepie jako wezwanie na przyjęcia w MPOS lub POS chmury. Po wprowadzeniu ilości, które są odbierane w sklepie one mogą być zapisywane lokalnie dla żadnych dodatkowych modyfikacji. Można też zatwierdzić ilości i wysłać do centrali. W centrali, ilości, które zostały odebrane w sklepie są wyświetlane w usłudze Dynamics 365 dla operacji, w **odebrać** pola w zleceniu przesunięcia.

## <a name="stock-counts"></a>Stany zapasów z inwentaryzacji
Inwentaryzacje mogą być zaplanowane lub niezaplanowane. Zaplanowana inwentaryzacja jest inicjowana z poziomu centrali, która określa towary podlegające inwentaryzacji. Siedziba tworzy dokument inwentaryzacji, jakie mogą być odbierane w sklepie, gdzie ilości rzeczywistej dostępnych zapasów są wprowadzane w MPOS lub POS chmury. Nieplanowane inwentaryzacje są inicjowane w sklepie i ilości rzeczywistej dostępnych zapasów są aktualizowane w MPOS lub POS chmury. W odróżnieniu od zaplanowane inwentaryzacje Nieplanowane inwentaryzacje mają listę wstępnie zdefiniowanych elementów. Po zakończeniu inwentaryzacja dowolnego typu jest zatwierdzana wysyłana do centrali. W centrali dane podlegają sprawdzeniu i zaksięgowaniu.




