---
title: Synchronizacja cen i rabatów międzyfirmowych
description: W tym temacie wyjaśniono synchronizację cen i rabatów dla międzyfirmowych zamówień sprzedaży i zamówień zakupu
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
ms.openlocfilehash: 90fa2244b5947c37b8498d1c70cddf894979f931
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673642"
---
# <a name="synchronize-intercompany-prices-and-discounts"></a>Synchronizacja cen i rabatów międzyfirmowych

[!include [banner](../../includes/banner.md)]

Rabaty i ceny są zawsze synchronizowane między międzyfirmowym zamówieniem sprzedaży a międzyfirmowym zamówieniem zakupu. Można także wybrać opcję umożliwiającą synchronizację cen i rabatów do/z oryginalnym zamówieniem sprzedaży, tak aby wszystkie zamówienia miały te same ceny i rabaty. Można to zrobić ze strony **międzyfirmowej** dostępnej z karty **Ogólne** na stronie listy **Wszyscy odbiorcy** — ze **sprzedaży i marketingu** albo z działu zaopatrzenia i **sourcingu**.

Pole **Cena i rabat** jest zsynchronizowane z wierszem międzyfirmowego zamówienia sprzedaży. Oznacza to, że zaznaczenie pól **Zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** umożliwia zmianę pomiędzy międzyfirmowym zamówieniem sprzedaży i międzyfirmowym zamówieniem zakupu. Zmiana ceny jednostkowej, jednostki cenowej lub opłaty za sprzedaż na międzyfirmowym zamówieniu sprzedaży wyznacza cenę w wierszu międzyfirmowego zamówienia zakupu.

Jeśli pola **zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** są włączone na międzyfirmowe zamówienie sprzedaży lub międzyfirmowe zamówienie zakupu, cenę lub rabat można zmienić ręcznie w obu zamówieniach. W przeciwnym razie nie wolno.

Jeśli pola **zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** nie są włączone w międzyfirmowym zamówieniu sprzedaży, nie można ręcznie zmienić ceny (lub opłat) ani rabatu w międzyfirmowym zamówieniu sprzedaży.

Jeśli pola **zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** nie są włączone w międzyfirmowym zamówieniu zakupu, nie można ręcznie zmienić ceny (lub opłat) ani rabatu w międzyfirmowym zamówieniu zakupu.

Jeśli pola **zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** są włączone zarówno w międzyfirmowym zamówieniu zakupu, jak i międzyfirmowym zamówieniu sprzedaży, możesz ręcznie wprowadzić zmiany w obu zamówieniach. Może to jednak spowodować sytuację, w której aktualizacje dokonane przez jedną osobę zostaną zastąpione aktualizacjami dokonanymi przez inną osobę w innej firmie w tym samym zamówieniu.

> [!NOTE]
> Po włączeniu pola **Cena i rabat** w międzyfirmowym zamówieniu zakupu i międzyfirmowym zamówieniu sprzedaży kontrola cen nie jest możliwa.

Najważniejszą wskazówką pozwalającą uniknąć konfliktów tego typu jest dopuszczanie tylko zmian na międzyfirmowym zamówieniu sprzedaży lub międzyfirmowym zamówieniu zakupu. W tym celu należy wyzwomnić pola **Zezwalaj na edycję ceny** i **Zezwalaj na edycję rabatu** w jednym z tych zamówień.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
