---
title: Odwołanie do oryginalnych faktur w fakturach korygujących (faktury od dostawcy)
description: W tym temacie opisano sposób tworzenia odwołania do oryginalnej faktury podczas tworzenia noty kredytowej.
author: v-oloski
ms.date: 09/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-oloski
ms.search.validFrom: 2021-09-23
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6114ffb4d3b9e942887cbfa10c6039b0d73af7e1
ms.sourcegitcommit: 86f0574363fb869482ef73ff294f345f81d17c5b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7562233"
---
# <a name="reference-original-invoices-in-credit-notes-vendor-invoices"></a>Odwołanie do oryginalnych faktur w fakturach korygujących (faktury od dostawcy)

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia odwołania do oryginalnej faktury podczas tworzenia noty kredytowej.

## <a name="prerequisites"></a>Wymagania wstępne

W obszarze roboczym **Zarządzanie funkcjami** włącz funkcję **Włączanie fakturowania po stronie kredytowej dla faktur od dostawców**. Aby uzyskać więcej informacji, zapoznaj się z tematem [Zarządzanie funkcjami — omówienie](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Funkcjonalność opisana w tym temacie dotyczy następujących dokumentów biznesowych.

**Rozrachunki z dostawcami:**

- Zamówienie zakupu
- Arkusz faktur
- Rejestr faktur

**Księga główna:**

- Arkusze finansowe

## <a name="define-a-reference-to-an-original-invoice"></a>Zdefiniuj odniesienie do oryginału faktury

Użyj poniższych procedur, aby zdefiniować odniesienie do oryginalnej faktury w określonych typach dokumentów biznesowych.

### <a name="vendor-credit-note-purchase-order"></a>Nota kredytowa dostawcy (zamówienie zakupu)

1. Wybierz kolejno opcje **Rozrachunki z dostawcami** \> **Zamówienia zakupu** \> **Wszystkie zamówienia zakupu**.
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