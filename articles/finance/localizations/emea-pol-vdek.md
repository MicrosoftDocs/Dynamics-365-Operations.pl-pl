---
title: Deklaracja VAT z ewidencjami (JPK-V7M, VDEK)
description: Ten artykuł zawiera informacje o deklaracji VAT z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.
author: AdamTrukawka
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: atrukawk
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
ms.openlocfilehash: f99838a4c76bbd440ba3b57af6270e4778ab8f30
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280660"
---
# <a name="vat-declaration-with-registers-jpk-v7m-vdek"></a>Deklaracja VAT z ewidencjami (JPK-V7M, VDEK)

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje na temat deklaracji podatku od wartości dodanej (VAT) z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.

Od 1 października 2020 firmy w Polsce są zobowiązane do raportowania podatku VAT w dokumencie elektronicznym, który składa się z jednolitego pliku kontrolnego VAT (JPK_VAT) razem z deklaracją (jednolity plik kontrolny VDEK). Żądany dokument elektroniczny zawiera następujące informacje:

- Oba rekordy VAT (zestawienie informacji o zakupach i sprzedaży, które są generowane z rekordów VAT przedsiębiorcy za dany okres)
- Deklaracja VAT (Deklaracja VAT-7)

Począwszy od wersji Microsoft Dynamics 365 Finance **10.0.29**, funkcja JPK-V7M obsługuje składanie deklaracji VAT dla [wielu rejestracji VAT](emea-multiple-vat-registration-numbers.md).

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można przygotować aplikację Finance do raportowania JPK_V7M, procesy biznesowe i system muszą spełniać następujące warunki:

- Na stronie **Urzędy skarbowe** (**Podatek** \> **Podatek pośredni** \> **Podatek** \> **Urzędy skarbowe**), dla urzędu skarbowego, który jest skojarzony z kodami podatku używanymi w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK-V7M, pole **Układ raportu** musi być ustawione na wartość **Domyślne**. Aby uzyskać więcej informacji dotyczące sposobu konfigurowania urzędów skarbowych, zobacz [Konfigurowanie urzędów skarbowych](../general-ledger/tasks/set-up-sales-tax-authorities.md).
- Jeśli księgowane są transakcje podatkowe, które muszą zostać uwzględnione w raporcie JPK-V7M, należy ustawić pole **Data ewidencji VAT**.
- Na stronie **Kody podatku** (**Podatek** \> **Podatek pośredni** \> **Podatek** \> **Kody podatku**) dla kodów podatku używanych w transakcjach podatkowych, które muszą zostać uwzględnione w raporcie JPK-V7M pole **Typ podatku** musi być ustawione na wartość **Standardowy VAT** lub **Obniżony VAT**.
- Na stronie **Kody podatku** dla kodów podatków używanych w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK-V7M, kody raportowania podatku używane w formacie raportu elektronicznego (ER) muszą być odpowiednio zdefiniowane.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
