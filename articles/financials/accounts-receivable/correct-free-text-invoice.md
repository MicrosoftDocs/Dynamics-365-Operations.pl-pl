---
title: "Korekta faktury niezależnej"
description: "W tym artykule wyjaśniono, jak poprawić zaksięgowaną fakturę niezależną i wystawić ją ponownie jako skorygowaną fakturę."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: cbae4c444db29a8dc7f3040aa78e45c0da092efd
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="correct-a-free-text-invoice"></a>Korekta faktury niezależnej

[!INCLUDE [banner](../includes/banner.md)]

W tym artykule wyjaśniono, jak poprawić zaksięgowaną fakturę niezależną i wystawić ją ponownie jako skorygowaną fakturę.

Aby skorygować fakturę niezależną, która została zaksięgowana, otwórz ją. Na stronie **Faktura** wybierz opcję **Anuluj**, a następnie wybierz opcję **Poprawianie faktury**. Wybierz kod przyczyny, dodaj komentarz i wybierz datę dla nowej, poprawionej faktury. Możesz zmodyfikować skorygowaną fakturę i zaksięgować ją. 

Podczas księgowania skorygowanej faktury tworzona jest faktura anulująca dla kwoty po stronie kredytowej, która jest równa kwocie pierwotnej faktury. W efekcie saldo połączone oryginalnej faktury i faktury anulującej wynosi 0 (zero). Faktura anulująca jest księgowana względem oryginalne faktury. 

Po zaksięgowaniu skorygowanej faktury, masz trzy faktury:

-   **Oryginalna faktura** — faktura, która zawiera informacje, które korygujesz.
-   **Faktura anulująca** — wygenerowana przez system faktura kredytowa, utworzona w celu anulowania faktury, która jako ostatnia została skorygowana.
-   **Skorygowana faktura** — faktura, która zawiera informacje faktury skorygowanej.

Faktury anulujące i korygujące można określić na dwa sposoby:

-   Strona **Wszystkie faktury niezależne** zawiera kolumnę **korekta**, na której widać, które faktury są fakturami anulującymi, a które są fakturami korygującymi.
-   Nagłówek faktury niezależnej pokazuje stan **Anulowanie faktury „\[numer faktury\]”** lub **Skorygowana faktura „\[numer faktury\]”**.

> [!NOTE]
> Ta funkcja jest dostępna tylko, jeśli wybrany jest klucz konfiguracji **Poprawianie faktury niezależnej**.




