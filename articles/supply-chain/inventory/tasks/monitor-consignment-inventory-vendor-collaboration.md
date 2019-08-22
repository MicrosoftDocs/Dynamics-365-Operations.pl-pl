---
title: Monitorowanie zapasów konsygnacyjnych poprzez współpracę z dostawcami
description: Ta procedura przedstawia sposób wykorzystywania portalu współpracy z dostawcami do zobaczenia informacji o poziomie zapasów produktu, które umieszczono w konsygnacji u odbiorcy.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentProductReceiptLines, PurchVendorPortalConfirmedOrders, DefaultDashboard, ConsignmentVendorPortalOnhand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dfbe5e9de7b700d991e0826fb4387de416ce242a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845403"
---
# <a name="monitor-consignment-inventory-using-vendor-collaboration"></a>Monitorowanie zapasów konsygnacyjnych poprzez współpracę z dostawcami

[!include [task guide banner](../../includes/task-guide-banner.md)]

Ta procedura przedstawia sposób wykorzystywania portalu współpracy z dostawcami do zobaczenia informacji o poziomie zapasów produktu, które umieszczono w konsygnacji u odbiorcy. Można również monitorować zużycie zapasów, gdy odbiorca przejmie własność zapasów. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej USMF. Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="view-consumed-inventory"></a>Wyświetlanie zużytych zapasów
1. Wybierz kolejno opcje Portal współpracy z dostawcami > Zapasy konsygnacyjne > Produkty odebrane z zapasów konsygnacyjnych.
    * Na liście widać wiersze przyjęcia produktów, które zostały wygenerowane podczas zmiany własności zapasów konsygnacyjnych z dostawcy na odbiorcę. Może być konieczne przewinięcie w prawo, aby zobaczyć ilości i inne informacje. Informacje na tej liście służą do generowania faktur dla odbiorcy. Można również wyeksportować dane do programu Microsoft Excel.   
2. Kliknij opcję Wyświetl zamówienie zakupu.
3. Rozwiń sekcję Szczegóły wiersza.
    * Wiersz jest oznaczony jako Konsygnacja, a sekcja nagłówka pokazuje, że zamówienie zakupu ma stan Otrzymane.  
4. Zamknij stronę.

## <a name="view-on-hand-inventory"></a>Wyświetlianie zapasów na stanie
1. Wybierz kolejno opcje Portal współpracy z dostawcami > Zapasy konsygnacyjne > Dostępne zapasy konsygnacyjne.
    * Strona Dostępne zapasy konsygnacyjne pokazuje zapasy istniejące w magazynie odbiorcy, których jesteś właścicielem. Można pokazać dodatkowe wymiary, takie jak oddział i magazyn, klikając kartę Wyświetl wymiary.   

