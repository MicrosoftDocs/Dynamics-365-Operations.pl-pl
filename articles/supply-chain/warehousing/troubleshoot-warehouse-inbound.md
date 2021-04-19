---
title: Rozwiązywanie problemów dotyczących przychodzących operacji magazynowych
description: W tym temacie opisano, jak rozwiązać typowe problemy, które mogą wystąpić podczas pracy z przychodzącymi operacjami magazynowymi w Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: f0ea2ee208cdbb8f9fa6668bbcb6e15252a7c1b1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828233"
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

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a>Podczas rejestrowania zamówień przychodzących wyświetlany jest następujący komunikat o błędzie: „Ilość jest nieprawidłowa”.

### <a name="issue-description"></a>Opis problemu

Jeśli w polu **Zasady grupowania identyfikatorów** jest ustawiona wartość *Użytkownik zdefiniowany* dla elementu menu urządzenia przenośnego używanego do rejestrowania zamówień przychodzących, pojawia się komunikat o błędzie („Ilość jest prawidłowa”) i nie można zakończyć rejestracji.

### <a name="issue-cause"></a>Przyczyna problemu

Gdy *Zdefiniowana przez użytkownika* jest używana jako zasada grupowania numerów identyfikacyjnych, system rozdziela przychodzące zapasy na osobne numery identyfikacyjne, zgodnie z grupą sekwencji jednostek. Jeśli do śledzenia otrzymywanego towaru używane są numery partii lub serii, ilości każdej partii lub serii należy określić zgodnie z zarejestrowanym numerem identyfikacyjnym. Jeśli ilość określona dla numeru rejestracyjnego przekracza ilość, która nadal musi zostać odebrana dla bieżących wymiarów, zostanie wyświetlony komunikat o błędzie.

### <a name="issue-resolution"></a>Rozwiązywanie problemów

Podczas rejestrowania towaru za pomocą elementu menu urządzenia przenośnego, w którym w polu **Zasady grupowania numerów identyfikacyjnych** jest ustawiona wartość *Zdefiniowana przez użytkownika*, system może wymagać potwierdzenia lub wprowadzenia numerów identyfikacyjnych, numerów partii lub numerów seryjnych.

Na stronie potwierdzenia dla bieżącego numeru identyfikacyjnego system pokazuje ilość zaalokowana dla bieżącego numeru identyfikacyjnego. Na stronach potwierdzenia przetwarzania wsadowego lub seryjnego w systemie będzie pokazywana ilość, jaka musi zostać jeszcze odebrana dla bieżącego numeru seryjnego. Zawiera również pole, w którym można wprowadzić ilość do rejestracji dla tej kombinacji numeru identyfikacyjnego i numeru seryjnego. W tym przypadku upewnij się, że ilość zarejestrowana dla tego numeru identyfikacyjnego nie przekracza ilości, która musi być jeszcze otrzymana.

Jeśli podczas rejestracji zamówienia przychodzącego generowana jest zbyt wiele numerów identyfikacyjnych, wartość pola **Zasady grupowania numerów identyfikacyjnych** może zostać zmieniona na *Grupowanie numerów identyfikacyjnych*, można przypisać do towaru nową grupę sekwencji jednostek lub można dezaktywować opcję **Grupowania numerów identyfikacyjnych** dla tej grupy sekwencji jednostek.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
