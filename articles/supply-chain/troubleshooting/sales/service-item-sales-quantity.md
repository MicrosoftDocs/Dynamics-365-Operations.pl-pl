---
title: Nie można ustawić usługi w wierszu oferty sprzedaży
description: Podczas pracy z ofertami sprzedaży nie można ustawić ilości sprzedaży dla produktów, które są usługami, ponieważ nie ma żadnych fizycznych towarów do zliczania.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: ea0f8f246e95f90b6ac5e78ee63950c9ca836a0e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477349"
---
# <a name="cant-change-the-sales-quantity-of-a-service-item-on-a-sales-quotation-line"></a>Nie można zmienić ilości sprzedaży usługi w wierszu oferty sprzedaży

## <a name="symptoms"></a>Objawy

W przypadku próby ustawienia ilości sprzedaży (pole **SalesQty**) dla towaru typu *Usługa* w wierszu oferty sprzedaży zostanie wyświetlony następujący komunikat:

> Aktualizacja jest niedozwolona dla pola Ilość.

## <a name="cause"></a>Powód

Jest to celowe. Nie można skonfigurować ilości sprzedaży dla produktów, które są pozycjami serwisu. Jeśli na przykład oferowana jest usługa instalowania towaru, nie ma sensu, aby było możliwe zarejestrowanie ilości z powodu braku fizycznego towaru do zliczenia. Istnieje tylko usługa.
