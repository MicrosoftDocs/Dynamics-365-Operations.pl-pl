---
title: Deklaracja VAT z ewidencjami (JPK-V7M, VDEK)
description: Ten artykuł zawiera informacje o deklaracji VAT z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.
author: liza-golub
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, TaxAuthority, TaxReportCollection, TaxTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: elgolu
ms.openlocfilehash: 637df1eb87627fa4ff8dd5f4212c2b2847cbbb88
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903002"
---
# <a name="vat-declaration-with-registers-jpk-v7m-vdek"></a>Deklaracja VAT z ewidencjami (JPK-V7M, VDEK)

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje na temat deklaracji podatku od wartości dodanej (VAT) z rejestrami (znanymi również jako JPK-V7M, VDEK) w Polsce.

Od 1 października 2020 firmy w Polsce są zobowiązane do raportowania podatku VAT w dokumencie elektronicznym, który składa się z jednolitego pliku kontrolnego VAT (JPK_VAT) razem z deklaracją (jednolity plik kontrolny VDEK). Żądany dokument elektroniczny zawiera następujące informacje:

- Oba rekordy VAT (zestawienie informacji o zakupach i sprzedaży, które są generowane z rekordów VAT przedsiębiorcy za dany okres)
- Deklaracja VAT (Deklaracja VAT-7)

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można przygotować aplikację Microsoft Dynamics 365 Finance do raportowania JPK_V7M, procesy biznesowe i system muszą spełniać następujące warunki:

- Na stronie **Urzędy skarbowe** (**Podatek** > **Podatek pośredni** > **Podatek** > **Urzędy skarbowe**), dla urzędu skarbowego, który jest skojarzony z kodami podatku używanymi w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK_V7M, pole **Układ raportu** musi być ustawione na wartość **Domyślne**. Aby uzyskać więcej informacji dotyczące sposobu konfigurowania urzędów skarbowych, zobacz [Konfigurowanie urzędów skarbowych](../general-ledger/tasks/set-up-sales-tax-authorities.md).
- Jeśli księgowane są transakcje podatkowe, które muszą zostać uwzględnione w raporcie JPK_V7M, należy ustawić pole **Data ewidencji VAT**.
- Na stronie **Kody podatku** (**Podatek** > **Podatek pośredni** > **Podatek** > **Kody podatku**) dla kodów podatku używanych w transakcjach podatkowych, które muszą zostać uwzględnione w raporcie JPK_V7M pole **Typ podatku** musi być ustawione na wartość **Standardowy VAT** lub **Obniżony VAT**.
- Na stronie **Kody podatku** dla kodów podatków używanych w transakcjach podatkowych, które muszą być uwzględnione w raporcie JPK_V7M, kody raportowania podatku używane w formacie raportu elektronicznego (ER) muszą być odpowiednio zdefiniowane.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
