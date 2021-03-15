---
title: Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970262"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Zgłaszany jest następujący komunikat o błędzie: Wygenerowano „Zlecenie kontroli jakości %1. Nie można odnaleźć profilu grupy. Sprawdź konfigurację".

### <a name="issue-description"></a>Opis problemu

Ten komunikat o błędzie jest związany z procesem odbierania, w którym jest włączona funkcja zarządzania jakością (QMS). W zależności od konfiguracji w danym środowisku dodatkowe szczegóły dotyczące transakcji, która generuje komunikat o błędzie, mogą pomóc w rozwiązaniu problemu.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Najpierw przejrzyj ustawienia [pobierania dla grupy](set-up-cluster-picking.md) i upewnij się, że profile grup są skonfigurowane poprawnie. Nie można skorzystać z elementu menu urządzenia przenośnego do pobierania grup, dopóki nie zostaną skonfigurowane Profile grup. W zależności od środowiska konieczne może być również przejrzenie innych pokrewnych konfiguracji.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>Odbieranie mieszanego numeru identyfikacyjnego nie działa dla kodu dyspozycji z wyjątkiem kredytu.

### <a name="issue-description"></a>Opis problemu

Jeśli pole **Akcja** dla kodu dyspozycji ma wartość *Kredyt* lub *Odpadki*, do przetwarzania zwróconych towarów można używać tylko elementu menu [Odbieranie mieszanych numerów identyfikacyjnych](mixed-license-plate-receiving.md).

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Firma Microsoft oceniła ten błąd i ustaliła, że jest to ograniczenie funkcji. Obecnie tylko [kody dyspozycji](../service-management/set-up-disposition-codes.md), w których pole **Akcja** ma wartość *Kredyt* lub *Odpadki*, są obsługiwane w przypadku otrzymywania mieszanego numeru identyfikacyjnego.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Kiedy uruchamiam zadanie okresowe Aktualizuj przyjęcia produktów, niepotwierdzone zamówienia zakupu są potwierdzane.

### <a name="issue-description"></a>Opis problemu

Po uruchomieniuzadania okresowego *Aktualizowanie dokumentów przyjęcia produktów* system automatycznie potwierdza niepotwierdzone zamówienia zakupu ze stanem transakcji magazynowej *Zarejestrowane*.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Nowa funkcja obsługi ładunków przychodzących *Przekroczenie przyjmowania ilości ładunku* rozwiązuje ten problem. Aby włączyć tę funkcję, przejdź do [Zarządzania funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i włącz następujące funkcje (w kolejności, w jakiej są wymienione):

1. Skojarz transakcje magazynowe zamówienia zakupu z ładunkiem
1. Przyjęcie nadmiernej ilości obciążenia pracą

Aby uzyskać więcej informacji, zajrzyj do [Księguj zarejestrowane ilości produktów na podstawie zamówień zakupu](inbound-load-handling.md#post-registered-quantities).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]