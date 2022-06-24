---
title: Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień
description: Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: c01a2fda54e198a43fa84ae83686fc1701958b6b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890276"
---
# <a name="payments-are-automatically-settled-before-orders-are-invoiced-or-shipped"></a>Płatności są automatycznie rozliczane przed zafakturowaniem lub wysyłkami zamówień

[!include [banner](../../includes/banner.md)]

Ten artykuł zawiera wskazówki dotyczące rozwiązywania problemów, które mogą pomóc w sytuacji, gdy płatność zostanie rozliczona w portalu Adyen natychmiast po zrównaniu zamówienia, nawet jeśli zamówienie sprzedaży nie zostało zafakturowane ani wysłane.

## <a name="description"></a>opis

Po złożeniu zamówienia płatność jest natychmiast rozliczana w portalu Adyen, mimo że zamówienie sprzedaży nie zostało zafakturowane ani wysłane.

## <a name="resolution"></a>Rozdzielczość

### <a name="configure-manual-capture-for-e-commerce-payments-in-the-adyen-portal"></a>Konfigurowanie ręcznego przechwytywania płatności handlu elektronicznego w portalu Adyen

Aby skonfigurować ręczne przechwytywanie dla płatności handlu elektronicznego w portalu Adyen, wykonaj następujące kroki.

1. Zaloguj się do portalu usługi Adyen.
1. W prawym górnym rogu wybierz konto handlowca dla kanału handlu elektronicznego.
1. Na górnym pasku nawigacyjnym wybierz opcję **Konto**, a następnie wybierz opcję **Ustawienia**.
1. W polu **Przechwyć opóźnienie** wybierz opcję **ręcznie**.

    ![Ustawienie przechwycenia opóźnienia w portalu Adyen.](media/adyen-capture-delay.jpg)

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przechwycenie płatności Adyen](https://docs.adyen.com/point-of-sale/capturing-payments)

[Dynamics 365 Payment Connector dla Adyen](../dev-itpro/adyen-connector.md)

[Skonfiguruj łącznik płatności Adyen dla Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
