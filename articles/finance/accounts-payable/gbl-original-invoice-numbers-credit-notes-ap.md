---
title: Odwołanie do oryginalnych faktur w fakturach korygujących (faktury od dostawcy)
description: W tym artykule opisano sposób tworzenia odwołania do oryginalnej faktury podczas tworzenia noty kredytowej.
author: AdamTrukawka
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.search.form: ''
ms.openlocfilehash: 39cf4eb7eef1a83abeb7bd44fa7b2abefee0806e
ms.sourcegitcommit: 8eb0cafe5ad20be2c4fff684e88d7d3f2249f820
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409672"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Odwołanie do oryginalnych faktur w fakturach korygujących (faktury od dostawcy)

[!include [banner](../includes/banner.md)]

W niektórych krajach i regionach istnieje wymóg prawny, aby wydrukowane noty kredytowe lub trasy raportowania zawierały odniesienia do oryginalnych faktur. W tym artykule opisano sposób tworzenia odwołania do oryginalnej faktury podczas tworzenia noty kredytowej.

## <a name="prerequisites"></a>Wymagania wstępne

W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Włączanie fakturowania po stronie kredytowej dla faktur od dostawców**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Funkcjonalność opisana w tym artykule dotyczy następujących dokumentów biznesowych.

**Rozrachunki z dostawcami:**

- Zamówienie zakupu
- Arkusz faktur
- Rejestr faktur

**Księga główna:**

- Arkusze finansowe

## <a name="define-a-reference-to-an-original-invoice"></a>Zdefiniuj odniesienie do oryginału faktury

Definiowanie odwołania do oryginalnej faktury obejmuje następujące kroki wysokiego poziomu:
1. Tworzenie i księgowanie faktury od dostawcy.
2. Tworzenie faktury kredytowej od dostawcy.
3. Używanie funkcji fakturowania po stronie kredytowej, aby połączyć fakturę z fakturą korygującą.
4. Księgowanie faktury korygującej.

Użyj poniższych procedur, aby zdefiniować odniesienie do oryginalnej faktury w określonych typach dokumentów biznesowych.

### <a name="vendor-credit-note-purchase-order"></a>Nota kredytowa dostawcy (zamówienie zakupu)

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** > **Zamówienia zakupu** > **Wszystkie zamówienia zakupu**.
2. Utwórz nowe zamówienie zakupu lub użyj istniejącego, aby utworzyć notę kredytową.
3. W okienku akcji na karcie **Faktura** w grupie **Wprowadzenie** wybierz **Księgowanie fakturowania po stronie kredytowej**.
4. Wprowadź przyczynę korekty i odniesienie do oryginalnej faktury.

### <a name="vendor-credit-note-ledger-journals"></a>Faktura koryguje od dostawcy (arkusze księgi)

1. Wykonaj jeden z następujących kroków:

    - Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Arkusze faktur**.
    - Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Rejestr faktur**.
    - Wybierz kolejno opcje **Księga główna** \> **Wpisy w arkuszu** \> **Arkusze finansowe**.

2. Utwórz nowy dziennik i nowe wiersze dziennika.
3. W okienku akcji wybierz pozycję **Funkcje** \> **Utwórz fakturę**.
4. Wprowadź przyczynę korekty i odniesienie do oryginalnej faktury.

> [!NOTE]
> Polecenie **Fakturowanie po stronie kredytowej** jest widoczne w załączniku arkusza ogólnego, jeśli w polu **Typ konta** jest ustawiona wartość **Dostawca**.
