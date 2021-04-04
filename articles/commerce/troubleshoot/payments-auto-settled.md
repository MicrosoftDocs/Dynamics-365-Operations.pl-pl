---
title: Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień
description: Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 788854a3119eb9ffaf839beb93a5bc15cdcd6387
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585483"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień

[!include [banner](../../includes/banner.md)]

Ten temat zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.

## <a name="description"></a>opis

Po złożeniu zamówienia płatność jest natychmiast rozliczana w portalu Adyen, mimo że zamówienie sprzedaży nie zostało zafakturowane ani wysłane.

## <a name="resolution"></a>Rozdzielczość

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Konfigurowanie ręcznego przechwytywania płatności handlu elektronicznego w portalu Adyen

Aby skonfigurować ręczne przechwytywanie dla płatności handlu elektronicznego w portalu Adyen, wykonaj następujące kroki.

1. Zaloguj się do portalu usługi Adyen.
1. W prawym górnym rogu wybierz konto handlowca dla kanału handlu elektronicznego.
1. Na górnym pasku nawigacyjnym wybierz opcję **Konto**, a następnie wybierz opcję **Ustawienia**.
1. W polu **Przechwyć opóźnienie** wybierz opcję **ręcznie**.

    ![Ustawienie przechwycenia opóźnienia w portalu Adyen](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przechwycenie płatności Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Łącznik płatności usługi Dynamics 365 dla Adyen](../dev-itpro/adyen-connector.md)

[Skonfiguruj łącznik płatności Adyen dla Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
