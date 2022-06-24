---
title: Synchronizacja opłat międzyfirmowych
description: W tym artykule wyjaśniono synchronizację opłat międzyfirmowych
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
ms.openlocfilehash: e7b3de3d7da7be6c1c8b5c3842862e7bccd78277
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857294"
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
