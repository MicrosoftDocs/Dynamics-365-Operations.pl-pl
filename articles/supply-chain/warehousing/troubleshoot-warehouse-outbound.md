---
title: Rozwiązywanie problemów dotyczących wychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z wychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 491803c5f9394f47a996c4e4c7fb8925e9464e644c99e5c1ab434706af6ad74e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756662"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Rozwiązywanie problemów dotyczących wychodzących operacji magazynowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z wychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Otrzymuję następujący komunikat o błędzie: „Nie można zwolnić zamówienia sprzedaży”.

### <a name="issue-description"></a>Opis problemu

Ten problem może wystąpić z kilku powodów. Na przykład zamówienie jest wstrzymane z zarządzaniem kredytami i nie można tworzyć żadnych wysyłek, dopóki nie zostanie wprowadzony prawidłowy adres pocztowy dla wszystkich wierszy sprzedaży, które są skojarzone z zamówieniem sprzedaży. Alternatywnie istnieje wstrzymanie zamówienia, na które należy się odnieść, zanim zamówienie zostanie zwolnione do magazynu. Ta wstrzymanie może być właściwe dla zamówienia lub na być na koncie odbiorcy.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Dodaj lub zaktualizuj adres w wierszach zamówienia sprzedaży i zamówienia, a następnie zwolnij zamówienie do magazynu. Zamówienia mogą być zwalniane do magazynu tylko wtedy, gdy mają prawidłowy adres dostawy (zgodnie z konfiguracją formatu adresu w module **Administrowanie organizacją**).

Zbadaj wstrzymanie zamówienia i rozwiąż problemy. Następnie usuń wstrzymanie z zamówienia lub klienta i zwolnij zamówienie do magazynu.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Wyświetlany jest następujący komunikat: „Wysyłka ładunku 1% została potwierdzona.” Nie są jednak księgowane żadne wiersze.

### <a name="issue-description"></a>Opis problemu

Wysyłka w ładunku została potwierdzona, ale dalsze księgowanie nie wystąpiło.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Potwierdzenie wysyłki nie ma wpływu na księgowanie. Właśnie aktualizuje stan wysyłki i ładunku. Księgowanie musi nastąpić w oddzielnym procesie.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Otrzymuję następujący komunikat o błędzie: „Nie można przetworzyć dostawy bezpośredniej dla magazynu 1%, ponieważ ma włączone zarządzanie magazynem. Proszę określić inny magazyn, który nie obsługuje zarządzania magazynem”.

### <a name="issue-description"></a>Opis problemu

Towar jest dodawany do wiersza sprzedaży w celu bezpośredniej dostawy z magazynu, który obsługuje zarządzanie magazynem (WMS). Ten komunikat o błędzie jest wyświetlany po zaktualizowaniu wiersza sprzedaży. 

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie usługa WMS nie obsługuje dostawy bezpośredniej. Dlatego też, aby można było skorzystać z dostawy bezpośredniej, należy wybrać pozycję i magazyn spoza WMS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]