---
title: Nieoczekiwana różnica między danymi żądania a danymi sesji podczas testowania
description: Nieoczekiwana różnica między danymi żądania a danymi sesji w wynikach weryfikacji zadań w aplikacji magazynowej.
author: mamuszal
ms.date: 03/11/2022
ms.topic: troubleshooting
ms.search.form: WHSValidatorRunInstance_executeRun
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mamuszal
ms.search.validFrom: 2022-03-11
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: da8f0506a76b0d0cc02bfc2e1bff01b4ddccb578
ms.sourcegitcommit: 941119133be1765f653d5d5270dfdf58466e1d07
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/17/2022
ms.locfileid: "8456943"
---
# <a name="unexpected-difference-between-request-and-session-data-during-testing"></a>Nieoczekiwana różnica między danymi żądania a danymi sesji podczas testowania

Kod błędu: WarehouseMobileDeviceRequestInputValidationError

## <a name="symptoms"></a>Objawy

Podczas używania struktury sprawdzania poprawności [zadań w aplikacji magazynowej](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/warehouse-app-task-validation-rsat) program validator zwraca następujący komunikat o błędzie:

> Nieoczekiwana różnica między danymi żądania a danymi sesji. Naruszono protokół XML urządzeń przenośnych magazynu. REQUEST_XML_TAMPERING

## <a name="cause"></a>Powód

Błąd występuje, gdy wynik ostatniego kroku, który został pomyślnie uruchomiony podczas uruchamiania testowego, nie pasuje do zarejestrowanych danych wejściowych dla następnego kroku. Taka sytuacja może wystąpić, ponieważ walidator zadań nie używa danych wyjściowych z poprzedniego kroku jako danych wejściowych dla kolejnego kroku. Zamiast tego są używane zarejestrowane dane XML jako dane wejściowe dla każdego kroku.

W większości przypadków błąd pojawia się po ponownym uruchomieniu zadania, ale test wymaga niektórych rekordów, które zostały zmodyfikowane lub usunięte przez poprzednie uruchomienie tego samego zadania.

## <a name="resolution"></a>Rozwiązanie

Test sprawdzania poprawności zadania aplikacji magazynu nie jest operacją idempotentną, ale modyfikuje dane źródłowe. Dlatego przed ponownego wykonania zadania może być konieczne zresetowanie odpowiednich danych.

1. Przejrzyj wyjściowy kod XML ostatniego pomyślnego kroku testu, aby określić, gdzie zakończył się test.
1. Sprawdź test i upewnij się, że wszystkie wymagane zamówienia sprzedaży, zamówienia przeniesienia, nagłówki pracy i inne rekordy są nadal obecne i w stanie oczekiwania.
1. Utwórz ponownie lub edytuj brakujące lub zmodyfikowane rekordy. Można również utworzyć nowe ustawienia i zaprojektować test, aby użyć prawidłowych istniejących rekordów.
