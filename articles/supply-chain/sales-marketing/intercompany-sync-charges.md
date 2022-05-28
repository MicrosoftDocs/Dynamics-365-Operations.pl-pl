---
title: Synchronizacja opłat międzyfirmowych
description: W tym temacie wyjaśniono synchronizację opłat międzyfirmowych
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 2c7f60786743cf750b2bb17ccc0dadf71d859766
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678583"
---
# <a name="synchronize-intercompany-charges"></a>Synchronizacja opłat międzyfirmowych

[!include [banner](../../includes/banner.md)]

Opłaty są synchronizowane tylko między międzyfirmowym zamówieniem sprzedaży a międzyfirmowym zamówieniem zakupu i synchronizacja zawsze jest przeprowadzana.

Jeśli w międzyfirmowym zamówieniu zakupu lub międzyfirmowym zamówieniu sprzedaży jest zaznaczone pole **Zezwalaj na edycję ceny**, to można ręcznie dodać opłatę dodatkową do międzyfirmowego zamówienia zakupu lub międzyfirmowego zamówienia sprzedaży. W przeciwnym razie nie wolno.

Jeśli pole **Zezwalaj na edycję ceny** nie jest zaznaczone w międzyfirmowym zamówieniu sprzedaży, nie można ręcznie dodać opłaty dodatkowej do międzyfirmowego zamówienia sprzedaży.

Jeśli pole **Zezwalaj na edycję ceny** nie jest zaznaczone w międzyfirmowym zamówieniu zakupu, nie można ręcznie dodać opłaty dodatkowej do międzyfirmowego zamówienia zakupu.

Jeśli pole **Zezwalaj na edycję ceny** jest włączone zarówno w międzyfirmowym zamówieniu zakupu, jak i międzyfirmowym zamówieniu sprzedaży, opłaty można dodać ręcznie do obu zamówień. Może to jednak spowodować nieprawidłowe dodanie wielu opłat.

Aby uniknąć tego typu konfliktów, najlepszym rozwiązaniem jest umożliwienie dodawania opłat do międzyfirmowego zamówienia sprzedaży lub międzyfirmowego zamówienia zakupu, ale nie do obu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
