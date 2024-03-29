---
title: Synchronizacja informacji międzyfirmowych o odbiorcy
description: W tym artykule wyjaśniono synchronizację informacji o klientach dla zamówień międzyfirmowych
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
ms.openlocfilehash: a3a67c9bcf93f88375d2d4d78d87175200626d50
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897524"
---
# <a name="synchronize-intercompany-customer-information"></a>Synchronizacja informacji międzyfirmowych o odbiorcy

[!include [banner](../../includes/banner.md)]

Jeśli pole **Informacje o odbiorcy** jest zaznaczone, informacje o odbiorcy są synchronizowane podczas tworzenia zamówienia sprzedaży lub gdy dokonywane są zmiany w danych odbiorcy, odwołaniu do dostawcy lub numerze zapotrzebowania odbiorcy.

Zawsze można zmienić wartość w tych polach synchronizacji. Możesz jednak określić, czy ta wartość jest kopiowana do innych zamówień międzyfirmowych, wybierając ten parametr. Jeśli pole **Informacje o odbiorcy** w międzyfirmowym zamówieniu sprzedaży jest zaznaczone, zmiany dokonywane w międzyfirmowym zamówieniu sprzedaży są synchronizowane z międzyfirmowym zamówieniem zakupu. Jeśli pole **Informacje o odbiorcy** jest zaznaczone również w międzyfirmowym zamówieniu zakupu, będzie ono synchronizowane z powrotem z oryginalnym zamówieniem sprzedaży.

> [!NOTE]
> Jeśli pole **Informacje o odbiorcy** zarówno w międzyfirmowym zamówieniu zakupu, jak i w międzyfirmowym zamówieniu sprzedaży jest zaznaczone, aktualizacje dokonane przez osobę w jednej firmie zostają unieważnione przez aktualizacje dokonane w tym samym zamówieniu przez inną osobę w innej firmie.

Najlepszą opcją jest włączenie pola **Informacje o odbiorcy** na międzyfirmowe zamówienie zakupu. Umożliwia to synchronizację między oryginalnym zamówieniem sprzedaży a międzyfirmowym zamówieniem zakupu oraz międzyfirmowym zamówieniem zakupu z międzyfirmowym zamówieniem sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
