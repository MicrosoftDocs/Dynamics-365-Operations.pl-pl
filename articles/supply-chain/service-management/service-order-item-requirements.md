---
title: Zapotrzebowanie na towary w zleceniu serwisowym
description: W tym temacie opisano wymagania dotyczące pozycji zlecenia serwisowego.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a6cd7e89e28b8fc00a8c09f51703995cd79ade5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674233"
---
# <a name="service-order-item-requirements"></a>Zapotrzebowanie na towary w zleceniu serwisowym

[!include [banner](../includes/banner.md)]

Można utworzyć zlecenie serwisowe do śledzenia i zarządzania usługami świadczonymi odbiorcom. Jeśli konieczne jest zarezerwowanie określonych towarów dla zlecenia serwisowego, można utworzyć zapotrzebowanie na pozycje magazynowe dla takiego zlecenia. Zapotrzebowania na towary mogą być realizowane bezpośrednio z magazynu lub mogą zainicjować zlecenie produkcyjne dla towaru.

Dzięki użyciu zapotrzebowań na towary zamiast transakcji towarowych można zaplanować czas dostawy dokładnie w momencie użycia towaru oraz można utworzyć zamówienie zakupu, dołączyć towar do struktury umowy handlowej i dołączyć zapotrzebowanie na towary w planie produkcyjnym.

Zapotrzebowania na towary dla zlecenia serwisowego są przetwarzane za pomocą projektu. W celu utworzenia zapotrzebowania na towary dla zlecenia serwisowego, takie zlecenie musi być powiązane z projektem.

Po utworzeniu zapotrzebowania na towary dla zlecenia serwisowego można je przejrzeć przy użyciu opcji **Projekt** dla pojedynczego zlecenia serwisowego albo przy użyciu formularza **Zamówienie sprzedaży**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Przeglądanie zapotrzebowania na towary dla zlecenia serwisowego

1. Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.
1. Wybierz **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**.
1. Wybierz kartę **Projekt**, a następnie sprawdź pole **Zlecenie serwisowe**, aby obejrzeć zlecenia serwisowe dla zapotrzebowania na towary.

## <a name="delete-service-orders-with-item-requirements"></a>Usuwanie zleceń serwisowych z zapotrzebowaniem na towary

Jeśli dla zlecenia serwisowego jest utworzone zapotrzebowanie na towary, to takiego zlecenia nie można usunąć. Należy najpierw usunąć zapotrzebowanie na towary i dopiero potem usunąć zlecenie serwisowe.

1. Przejdź do **Zarządzanie serwisem** \> **Wspólne** \> **Zlecenia serwisowe** \> **Zlecenia serwisowe**.
1. Wybierz **Wysyłka**, a następnie opcję **Zapotrzebowanie na towary**, a zostanie otwarty formularz **Zapotrzebowanie na towary**. Ten formularz zawiera listę zapotrzebowań na towary utworzonych dla określonego zlecenia serwisowego.
1. Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie wybierz przycisk **Usuń**.

– lub –

1. Przejdź do **Zarządzanie projektami i ich księgowanie** \> **Wspólne** \> **Projekty** \> **Wszystkie projekty**.
1. Otwórz projekt, w którego skład wchodzi zlecenie serwisowe, dla którego utworzono zapotrzebowanie na towary.
1. W formularzu **Projekty** w okienku po prawej stronie wybierz przycisk **Zapotrzebowanie na towary**. Formularz **Zapotrzebowanie na towary** będzie zawierał spis wszystkich zapotrzebowań na towary powiązanych z wybranym projektem.
1. Wybierz odpowiednie zapotrzebowanie na towar do usunięcia, a następnie wybierz przycisk **Usuń**.

## <a name="see-also"></a>Informacje dodatkowe

[Zapotrzebowanie na towary (formularz)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]