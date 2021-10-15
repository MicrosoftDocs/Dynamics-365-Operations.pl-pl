---
title: Międzyfirmowe konwersje walut
description: W tym temacie wyjaśniono konwersje walut dla transakcji międzyfirmowych
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 540849003d532ef2f0905c18332d9cb82a04cf7c
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548479"
---
# <a name="intercompany-currency-conversions"></a>Międzyfirmowe konwersje walut

[!include [banner](../../includes/banner.md)]

Gdy kod waluty w oryginalnym zamówieniu sprzedaży i międzyfirmowym zamówieniu zakupu różnią się, następujące pola są konwertowane na walutę, jeśli synchronizacja jest włączona:

- **Cena jednostkowa**
- **Opłaty związane** ze **sprzedażą lub związane z zakupami**
- **Dyskonto**
- **Rabat wspólny**

Te pola są następnie synchronizowane z wierszem międzyfirmowego zamówienia sprzedaży.

Jednak ponieważ waluta w międzyfirmowym zamówieniu zakupu i międzyfirmowym zamówieniu sprzedaży jest zawsze synchronizowana, następujące pola są synchronizowane bez przeliczania walut:

- **Cena jednostkowa**
- **Opłaty związane** ze **sprzedażą lub związane z zakupami**
- **Dyskonto**
- **Procent rabatu**
- **Rabat wspólny**
- **Procent rabatu wspólnego**

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
