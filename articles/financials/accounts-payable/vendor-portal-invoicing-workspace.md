---
title: Obszar roboczy fakturowania w portalu współpracy z dostawcami
description: W tym temacie wyjaśniono, jak wyświetlić faktury od dostawców i przesyłać faktury z obszaru roboczego Fakturowanie w portalu współpracy z dostawcami.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 221534
ms.assetid: c4ed62f3-d351-41d7-a2ad-790576cde4ab
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 149ed6887dd45710ab818ea496cac1f604cbc070
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835365"
---
# <a name="vendor-collaboration-invoicing-workspace"></a>Obszar roboczy fakturowania w portalu współpracy z dostawcami

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak wyświetlić faktury od dostawców i przesyłać faktury z obszaru roboczego Fakturowanie w portalu współpracy z dostawcami.

Obszar roboczy **Fakturowanie w portalu współpracy dostawcy** może służyć do przeglądania informacji o fakturach od dostawców i przesyłania faktur do programu Microsoft Dynamics 365 for Finance and Operations za pomocą funkcji przepływu pracy.


<a name="vendor-collaboration-invoicing-workspace"></a>Obszar roboczy fakturowania w portalu współpracy z dostawcami
----------------------------------------

### <a name="summary-tiles"></a>Kafelki podsumowania

Kafelki **Podsumowanie** prezentują przegląd faktur od wybranego dostawcy. Istnieje możliwość wyświetlania faktur według ich stanu.
-   Wersje robocze faktur nie zostały przesłane do przepływu pracy.
-   Przesłane niezatwierdzone faktury to takie faktury, które dostawca przesłał, ale nie zostały one jeszcze zaksięgowane w programie Finance and Operations.
-   Zatwierdzone niezapłacone faktury to takie faktury, które zostały zaksięgowane w programie Finance and Operations, ale ich jeszcze w całości nie opłacono.
-   Zapłacone faktury to takie faktury, które zostały w całości zapłacone w programie Finance and Operations.

Kliknięcie kafelka otwiera przefiltrowany widok strony **Lista faktur**.

### <a name="tabular-lists"></a>Listy tabelaryczne

W sekcji **Listy tabelaryczne** stan fakturowania dzieli się w podobny sposób, jak w kafelkach podsumowania: listy wersji roboczych i przesłanych niezatwierdzonych. W stanie Wersja robocza fakturę można przesłać do przepływu pracy lub usunąć. Ostatnia lista tabelaryczna to opcja pozwalająca odnaleźć faktury. Można filtrować podczas wyszukiwania, aby przyspieszyć wyszukiwanie.

### <a name="all-vendor-invoices-list-page"></a>Strona listy Wszystkie faktury od dostawcy

Na stronie listy **Faktury w portalu współpracy z dostawcami** można wyświetlić wszystkie zaksięgowane i niezaksięgowane faktury od dostawcy. Ta strona listy służy do wyświetlania stanu płatności faktur. Istnieją następujące stany płatności: niezaksięgowane, niezapłacone, częściowo zapłacone i w pełni zapłacone.
Tworzenie nowej faktury na podstawie zamówienia zakupu

Nową fakturę od dostawcy można utworzyć, wybierając akcję **Nowy** w obszarze roboczym **Fakturowanie w portalu współpracy z dostawcami**. Dostawca musi podać numer zamówienia zakupu i numer faktury. Domyślnie wszystkie wiersze z zamówienia zakupu dostawcy będą widoczne w nowej fakturze. Informacje dotyczące ilości i kosztu można edytować przed przesłaniem faktury dostawcy do przepływu pracy. Przed przesłaniem faktury można do niej dołączyć pliki, obrazy, notatki i adresy URL.

Aby uzyskać więcej informacji, zobacz [Współpraca z zewnętrznymi dostawcami](../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md)



