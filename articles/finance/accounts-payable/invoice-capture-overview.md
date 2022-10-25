---
title: Omówienie rozwiązania Invoice Capture
description: Ten artykuł zawiera informacje o rozwiązaniu Invoice Capture.
author: sunfzam
ms.date: 09/25/2022
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
ms.openlocfilehash: 76441220b93744527f412110db536601a2fa1dd9
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691210"
---
# <a name="invoice-capture-solution"></a>Rozwiązanie Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Ten artykuł zawiera informacje dotyczące rozwiązania Invoice Capture, które automatycznie tworzy faktury od dostawców na podstawie obrazów faktur cyfrowych.

Dział rozrachunków z dostawcami (AP) zarządza fakturami za otrzymane towary i usługi oraz je przetwarza. Księgowy działu AP weryfikuje dane na fakturach od dostawcy z następujących powodów:

- Aby uniknąć dodatkowego nakładu pracy, jeśli podczas zamykania okresu wymagane są korekty lub poprawki
- Aby terminowo płacić faktury od dostawców i zapobiegać stratom finansowym z powodu błędu lub oszustwa

Optyczne rozpoznawanie znaków (OCR) jest od kilku lat coraz częściej stosowane w różnych branżach. Drukowany tekst jest teraz często przekształcany do postaci cyfrowej, aby można było go elektronicznie edytować, wyszukiwać, przechowywać w małym rozmiarze i wyświetlać w trybie online. Tekst cyfrowy może być używany w procesach komputerowych, takich jak przetwarzanie poznawcze, tłumaczenie maszynowe, zamiana tekstu na mowę, kluczowe dane i wyodrębnianie znaczeń z tekstu.

Ewolucja technologii sztucznej inteligencji (AI) umożliwiła nowoczesnym rozwiązaniom OCR odczytywanie różnych formatów faktur od różnych dostawców bez konieczności interwencji ludzkich. Więcej firm rozpoznaje, że mogą zaoszczędzić nakłady pracy i zwiększyć dokładność dzięki przetwarzaniu faktur za pomocą automatyzacji, a nie ręcznego przetwarzania.

## <a name="system-landscape"></a>Krajobraz systemu

Na poniższej ilustracji przedstawiono główne składniki i kroki rozwiązania Invoice Capture.

[![Składniki i kroki w rozwiązaniu Invoice Capture.](./media/Invoice-capture2.png)](./media/Invoice-capture2.png)

## <a name="required-roles"></a>Wymagane role

W poniższej tabeli przedstawiono role wymagane do skonfigurowania i używania rozwiązania Invoice Capture.

| Rola          | Akcje | Systemy | Nazwy ról |
|---------------|---------|---------|-----------|
| Administrator | <ul><li>Konfiguracja środowisk na platformie Microsoft Power Platform.</li><li>Wdrażanie rozwiązań na platformie Microsoft Power Platform.</li><li>Konfigurowanie połączeń między rozwiązaniem Dynamics 365 i narzędziem AI Builder.</li><li>Konfigurowanie lokalizacji usługi Azure Data Lake Storage.</li></ul> | <ul><li>Dynamics 365</li><li>Microsoft Power Platform</li><li>Azure Data Lake Storage</li></ul> | <ul><li>Administrator usługi Dynamics 365</li><li>Administrator usługi Power Platform</li><li>Właściciel danych usługi Storage Blob</li></ul> |
| Twórca AI      | <ul><li>Obsługa przepływów.</li><li>Tworzenie niestandardowych modeli AI.</li></ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Twórcy obywatele</li></ul> |
| Urzędnik działu AP      | <ul><li>Przeglądanie obszaru tymczasowego faktur od dostawcy i podejmowanie powiązanych akcji.</li><ul> | <ul><li>Microsoft Power Platform</li></ul> | <ul><li>Nowa rola urzędnika działu AP na platformie Power Platform</li></ul> |
| Urzędnik działu AP      | <ul><li>Wykonywanie codziennych operacji jako urzędnik AP.</li><li>Przechodzenie do obszaru tymczasowego faktur od dostawcy.</li></ul> | <ul><li>Dynamics 365</li></ul> | <ul><li>Pracownik ds. rozrachunków z dostawcami</li></ul> |
  
Aby uzyskać więcej informacji dotyczących instalowania rozwiązania Invoice Capture, zobacz [Instalowanie rozwiązania Invoice Capture](../accounts-payable/install-invoice-capture.md).  
