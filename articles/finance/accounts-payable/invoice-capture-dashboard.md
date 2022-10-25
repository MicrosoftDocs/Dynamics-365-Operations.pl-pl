---
title: Pulpit nawigacyjny rozwiązania Invoice Capture
description: W tym artykule opisano pulpit nawigacyjny rozwiązania Invoice Capture.
author: sunfzam
ms.date: 10/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4c9000039488c1290f4ab992d7fe79b8ccac7b19
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690126"
---
# <a name="invoice-capture-solution-dashboard"></a>Pulpit nawigacyjny rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W rozwiązaniu Invoice Capture pulpit nawigacyjny zawiera wykresy przedstawiające omówienie zaimportowanych faktur. Wykresy te mogą ułatwić menedżerowi ds. rozrachunków z dostawcami (AP) analizowanie wydajności procesu generowania faktur. Menedżer AP może wyświetlać stan procesu generowania faktur, a przy zastosowaniu innych filtrów może także wyświetlać szczegóły.

## <a name="available-charts"></a>Dostępne wykresy

Na pulpicie nawigacyjnym są dostępne następujące wykresy:

- **Wszystkie przechwycone faktury według stanu** — na tym wykresie są przedstawiane następujące stany przechwyconej faktury. Wybierając stan, użytkownicy mogą filtrować przechwycone faktury na szczegółowej liście.

    - Przechwycone
    - Zakończ
    - W trakcie przeglądu
    - Przestarzałe

- **Łączna liczba przechwyconych faktur** — na tym wykresie jest przedstawiana liczba przechwyconych faktur według okresu. Użytkownicy mogą zmienić okres za pomocą listy rozwijanej.
- **Przechwycone faktury od najlepszych dostawców** — na tym wykresie jest przedstawiana łączna liczba faktur na dostawcę. Dostawcy z największą liczbą faktur są wyświetlani na początku.
- **Dni do zakończenia na fakturę z wyjątkami** — na tym wykresie jest przedstawiana średnia liczba dni wymagana do przechwycenia jednej faktury. Te informacje mogą ułatwić menedżerowi AP analizę czasu przetwarzania faktury, gdy jest wymagana ręczna interwencja. W przypadku trendu wzrostowego użytkownicy mogą przejrzeć szczegóły procesu i skorygować ustawienia, aby zredukować wymaganą liczbę dni.
- **Niekompletne faktury według czasu oczekiwania** — na tym wykresie jest przedstawiana liczba dni, przez które nie wygenerowano przechwyconej faktury na platformie planowania zasobów przedsiębiorstwa (ERP). Im większa liczba dni oczekiwania, tym dłuższy jest proces generowania faktury. Menedżer AP może przejść do szczegółów przechwyconych faktur i wygenerować faktury na platformie ERP.
