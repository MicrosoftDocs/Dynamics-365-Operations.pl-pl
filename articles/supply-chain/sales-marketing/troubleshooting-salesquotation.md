---
title: Rozwiązywanie problemów z ofertami sprzedaży
description: W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z ofertami sprzedaży.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 98011dbf22ff55b7651ce63557fa4a360130b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974767"
---
# <a name="troubleshoot-sales-quotations"></a>Rozwiązywanie problemów z ofertami sprzedaży

W tym temacie opisano, jak rozwiązać problemy, które mogą wystąpić podczas pracy z ofertami sprzedaży.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Nie można zmienić ilości sprzedaży oferty sprzedaży dla przedmiotu serwisu.

### <a name="issue-description"></a>Opis problemu

W przypadku próby ustawienia ilości sprzedaży (pole **SalesQty**) dla towaru typu *usługa* w wierszu oferty sprzedaży zostanie wyświetlony następujący komunikat: „Aktualizacja jest niedozwolona dla ilości w polu”.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Nie można skonfigurować ilości sprzedaży dla produktów, które są pozycjami serwisu. Jeśli na przykład usługa jest oferowana do zainstalowania towaru, nie ma sensu, aby było możliwe zarejestrowanie ilości z powodu braku fizycznego towaru. Istnieje tylko usługa.

