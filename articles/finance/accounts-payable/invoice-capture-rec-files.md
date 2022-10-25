---
title: Otrzymane pliki rozwiązania Invoice Capture
description: W tym artykule objaśniono sposób gromadzenia plików faktur z różnych źródeł w rozwiązaniu Invoice Capture.
author: sunfzam
ms.date: 10/13/2022
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
ms.openlocfilehash: 3c55540d11a67d4d4c4c8477d51cb6f1f5777767
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690129"
---
# <a name="invoice-capture-received-files"></a>Otrzymane pliki rozwiązania Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W aplikacji Invoice Capture strona **Odebrane pliki** jest głównym miejscem, w którym są odbierane pliki faktur z różnych źródeł.

## <a name="upload-invoice-files"></a>Przekazywanie plików faktur

Pracownicy ds. rozrachunków z dostawcami (AP) mogą przekazywać obrazy faktur, wybierając pozycję **Przekaż plik**, aby otworzyć okno dialogowe **Przekazywanie**. Gdy jeden z pracowników ds. AP wybierze plik, przycisk **Przekaż** stanie się dostępny.

## <a name="include-or-obsolete-invoice-files"></a>Uwzględnianie plików faktur lub oznaczanie ich jako przestarzałych

Użytkownicy mogą wybierać faktury z błędami lub ostrzeżeniami, a następnie uwzględniać faktury lub uznawać je za przestarzałe, wybierając odpowiedni przycisk w okienku akcji. Faktura oznaczona jako przestarzała nie będzie wyświetlana w widoku **Otrzymane pliki (przestarzałe)**.

## <a name="view-captured-invoices"></a>Wyświetlanie przechwyconych faktur

Po pomyślnym rozpoznaniu otrzymanego pliku informacje z przechwyconej faktury są zwracane przez model AI i wprowadzane w usłudze Microsoft Dataverse. Następnie pracownik ds. AP może sprawdzić szczegóły faktury, wybierając pozycję **Wyświetl przechwyconą fakturę**. W razie potrzeby użytkownicy mogą pobrać oryginalny plik faktury.
