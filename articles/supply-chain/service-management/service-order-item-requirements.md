---
title: Zapotrzebowanie na towary w zleceniu serwisowym
description: Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dc7c721af4b25e1586e546392518648110a3fb6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562307"
---
# <a name="service-order-item-requirements"></a>Zapotrzebowanie na towary w zleceniu serwisowym   

[!include [banner](../includes/banner.md)]


Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom. Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia. Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.

Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.

Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu. W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem.

Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można je przejrzeć przy użyciu opcji **Projekt** dla pojedynczego zlecenia serwisowego albo przy użyciu formularza **Zamówienie sprzedaży**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Przeglądanie zapotrzebowania na towary dla zlecenia serwisowego

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.

3.  Kliknij kartę **Projekt**, a następnie sprawdź pole **Zlecenie serwisowe**, aby obejrzeć zlecenia serwisowe dla zapotrzebowania na towary.

## <a name="delete-service-orders-with-item-requirements"></a>Usuwanie zleceń serwisowych z zapotrzebowaniem na towary

Jeśli dla zlecenia serwisowego jest utworzone zapotrzebowanie na towary, to takiego zlecenia nie można usunąć. Należy najpierw usunąć zapotrzebowanie na towary i dopiero potem usunąć zlecenie serwisowe.

1.  Kliknij kolejno opcje **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.

2.  Kliknij opcję **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**. Ten formularz zawiera listę zapotrzebowań na towary utworzonych dla określonego zlecenia serwisowego.

3.  Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.

– lub –

1.  Kliknij kolejno opcje **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.

2.  Otwórz projekt, w którego skład wchodzi zlecenie serwisowe, dla którego utworzono zapotrzebowanie na towary.

3.  W formularzu **Projekty** w okienku po prawej stronie kliknij przycisk **Zapotrzebowanie na towary**. Formularz **Zapotrzebowanie na towary** będzie zawierał spis wszystkich zapotrzebowań na towary powiązanych z wybranym projektem.

4.  Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie kliknij przycisk **Usuń**.

## <a name="see-also"></a>Informacje dodatkowe

[Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\))

