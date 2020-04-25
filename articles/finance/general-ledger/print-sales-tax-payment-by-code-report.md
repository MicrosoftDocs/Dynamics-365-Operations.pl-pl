---
title: Drukowanie raportu Płatności podatku według kodu
description: Ten temat zawiera informacje dotyczące ustawień i akcji wymaganych do wydrukowania raportu płatności podatku według kodu w walucie księgowania lub kodu podatku.
author: anasyash
manager: AnnBe
ms.date: 04/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 3c3b251aadfa997f453e60b0842f89a6f09eb9cb
ms.sourcegitcommit: 88347d0f0ac862a77f269a05f1801d30dc93586e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2020
ms.locfileid: "3260262"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Drukowanie raportu Płatności podatku według kodu 

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Aby wydrukować raport **płatności podatku według kodu**, przejdź do **Podatek** \> **Zapytania i raporty** \> **Raporty podatków** \> **Płatności podatku według kodu**. Domyślnie kwoty raportu są generowane w walucie rozliczeniowej firmy dla wszystkich kodów raportowania, które są konfigurowane na stronie **Kody raportowania podatku**.

Ten raport można również wygenerować, aby wyświetlić kwoty płatności podatku w walutach kodów podatków dla wszystkich kodów raportowania, które są przypisane do kodów podatków na stronie **Kody podatków**.

## <a name="turn-on-the-feature"></a>Włączanie funkcji

W obszarze roboczym **Zarządzanie funkcjami** włącz następującą funkcję: **Generuj raport płatności podatku według kodu w walucie kodu podatku**.

## <a name="run-the-report"></a>Uruchamianie raportu

1. Wybierz kolejno opcje **Podatek** \> **Zapytania i raporty** \> **Raporty podatków** \> **Płatności podatku według kodu**.
2. W polu **Waluta raportu** wybierz jedną z następujących wartości:

    - **Waluta rozliczeniowa** — umożliwia wydrukowanie kwot raportu w walucie rozliczeniowej.
    - **Waluta kodu podatku** — umożliwia wydrukowanie kwot raportu w walutach kodów podatków.

    ![Okno dialogowe Płatności podatku według kodu](media/Sales-tax-payment-by-code.png)

Na poniższej ilustracji przedstawiono przykład generowanego raportu. Raport wskazuje, że kod raportowania **101** ma walutę **EUR**, jeśli w polu **Waluta podatku** jest ustawiona wartość **EUR** dla kodu podatku, do którego przypisano kod raportowania.

![Przykład raportu Płatności podatku według kodu](media/Sales-tax-payment-by-code-2.png)
