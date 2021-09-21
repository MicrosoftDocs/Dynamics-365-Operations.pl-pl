---
title: Nie można zwolnić zamówienia sprzedaży z operacjami magazynu wychodzącego
description: Istnieje kilka przyczyn, z powodu których może zostać wyświetlony komunikat o błędzie, że nie można zwolnić zamówienia sprzedaży. Na tej stronie opisano przyczyny i sposób eliminowania tego problemu.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fca5ee1bc97545ea4de56d940fdedd320a6cfe84
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477323"
---
# <a name="sales-order-could-not-be-released-with-outbound-warehouse-operations"></a>Nie można zwolnić zamówienia sprzedaży z operacjami magazynu wychodzącego

## <a name="symptoms"></a>Objawy

Podczas pracy z wychodzącymi operacjami magazynowymi może zostać wyświetlony następujący komunikat o błędzie:

> Zamówienie sprzedaży nie może zostać zwolnione.

## <a name="cause"></a>Powód

Ten problem może wystąpić z kilku powodów. Na przykład zamówienie jest wstrzymane z zarządzaniem kredytami i nie można tworzyć żadnych wysyłek, dopóki nie zostanie wprowadzony prawidłowy adres pocztowy dla wszystkich wierszy sprzedaży, które są skojarzone z zamówieniem. Alternatywnie istnieje wstrzymanie zamówienia, na które należy się odnieść, zanim zamówienie zostanie zwolnione do magazynu. Ta wstrzymanie może być właściwe dla zamówienia lub na być na koncie odbiorcy.

## <a name="resolution"></a>Rozwiązanie

Dodaj lub zaktualizuj adres w wierszach zamówienia sprzedaży i zamówienia, a następnie zwolnij zamówienie do magazynu. Zamówienia mogą być zwalniane do magazynu tylko wtedy, gdy mają prawidłowy adres dostawy (zgodnie z konfiguracją formatu adresu w module **Administrowanie organizacją**).

Zbadaj wstrzymanie zamówienia i rozwiąż problemy. Następnie usuń wstrzymanie z zamówienia lub klienta i zwolnij zamówienie do magazynu.
