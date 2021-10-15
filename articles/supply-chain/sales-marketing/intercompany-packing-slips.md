---
title: Międzyfirmowe dokumenty dostawy
description: W tym temacie opisano sposób generowania i drukowania dokumentów dostawy dla transakcji międzyfirmowych
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
ms.openlocfilehash: 72d052d2daba90d49ba372fb3fb480bdd0877398
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548477"
---
# <a name="intercompany-packing-slips"></a>Międzyfirmowe dokumenty dostawy

## <a name="generate-intercompany-packing-slips"></a>Generuj międzyfirmowe dokumenty dostawy

[!include [banner](../../includes/banner.md)]

Jeśli pracujesz z dostawą bezpośrednią, dokument dostawy jest zawsze generowany automatycznie zarówno na międzyfirmowym zamówieniu zakupu, jak i na oryginalnym zamówieniu sprzedaży podczas generowania dokumentu dostawy na międzyfirmowym zamówieniu sprzedaży. Faktura międzyfirmowego zamówienia zakupu jest oparta na wcześniej wygenerowanym dokumencie dostawy międzyfirmowego zamówienia zakupu.

Jeśli wprowadzisz jakiekolwiek aktualizacje dokumentu dostawy w międzyfirmowym zamówieniu sprzedaży, te aktualizacje zostaną odzwierciedlone zarówno w międzyfirmowym zamówieniu zakupu, jak i w oryginalnym zamówieniu sprzedaży.

Jeśli nie pracujesz z dostawą bezpośrednią, musisz ręcznie wygenerować dokument dostawy na międzyfirmowym zamówieniu sprzedaży, międzyfirmowym zamówieniu zakupu i oryginalnym zamówieniu sprzedaży.

## <a name="print-intercompany-packing-slips"></a>Wydrukuj międzyfirmowe dokumenty przewozowe

[!include [banner](../../includes/banner.md)]

W przypadku pracy z dostawą bezpośrednią dokument dostawy może być wydrukowany automatycznie dla międzyfirmowego zamówienia zakupu i oryginalnego zamówienia sprzedaży podczas księgowania dokumentu dostawy w międzyfirmowym zamówieniu sprzedaży.

Aby automatycznie drukować dokumenty dostawy, na stronie **Międzyfirmowe** dla zamówień zakupu zaznacz oba pola automatycznie **drukuj dokument dostawy**.

Jeśli zaktualizujesz dokument dostawy w międzyfirmowym zamówieniu sprzedaży, zmiany są automatycznie odzwierciedlane w międzyfirmowym zamówieniu zakupu i oryginalnym zamówieniu sprzedaży.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
