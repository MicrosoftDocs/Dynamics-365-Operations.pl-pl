---
title: Przenieś podksięgę do księgi głównej
description: W tym artykule opisano możliwości rozwiązania związane z procesem przenoszenia księgi podrzędnej w księdze głównej.
author: RyanCCarlson2
ms.date: 12/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 7ef93b81ce37128f7ff400eb4034ffea01756038
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779861"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Przenieś podksięgę do księgi głównej

[!include [banner](../includes/banner.md)]

W tym artykule opisano możliwości rozwiązania, które są związane z regułami przenoszenia partii zapisów w arkuszu księgi podrzędnej.

W wersji 8.1 wprowadzono zmiany umożliwiające przeniesienie reguł, które nie wykluczają opcji **Synchronicznie**. Więcej informacji o zaniechaniu zawiera sekcja [Usuwanie lub przestarzałe funkcje w aplikacjach finansowych i operacyjnych](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Dostępne są następujące opcje przenoszenia partii w księdze podrzędnej:

- **Asynchroniczne** — Przeniesienie zapisów księgowych księgi podrzędnej do księgi głównej jest planowane natychmiast. Załącznik księgi głównej zostanie zarejestrowany, gdy tylko zasoby będą dostępne do przetworzenia tego żądania na serwerze.
- **Zaplanowane zadanie wsadowe** — Zapisy księgowe księgi podrzędnej, które muszą zostać przeniesione, są dodawane do kolejki przetwarzania w księdze głównej. Wpisy w kolejce będą przetwarzane w kolejności, w jakiej zostały odebrane. Każdy załącznik księgi głównej zaktualizuje konta w zaplanowanym czasie, jeśli dostępne są zasoby do przetwarzania zadania wsadowego na serwerze.

Dokonano ulepszeń w celu zwiększenia wydajności opcji **asynchronicznej**. Ta funkcja jest włączana pod nazwą **optymalizacji wydajności transferu podksięgi do księgi głównej**.

Funkcjonalność asynchronicznego przesyłania partii księgi podrzędnej pomaga usprawnić transfer danych z księgi podrzędnej do księgi głównej. Dzięki grupowaniu zestawów mniejszych transakcji i przenoszeniu transakcji w grupy, funkcjonalność efektywniej przetwarza transakcje. Podczas grupowania transakcji zasoby serwera przetwarzania wsadowego są używane efektywniej.

Asynchroniczne przenoszenie partii ksiąg podrzędnych wymaga skonfigurowania serwera przetwarzania wsadowego w trybie online oraz pracy, ponieważ zadania wsadowe zostały utworzone w celu natychmiastowego wykonania na serwerze przetwarzania wsadowego. Gdy jest włączona funkcja **optymalizacji wydajności transferu podksięgi do księgi głównej**, musi być również włączone zadanie wsadowe systemu **automatyzacji procesów** o nazwie **Sondowanie automatyzacji procesów**. Aby uzyskać więcej informacji, zobacz [Automatyzacja procesu](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

Zmiana wydajności na poziomie partii używa jednego cyklicznego zadania wsadowego dla wszystkich firm w systemie. W czasie wykonywania tworzone jest nowe zadanie wsadowe w celu przetworzenia wymaganych rekordów, które nie zostały jeszcze przeniesione. Więcej ustawień można kontrolować za pomocą strony **Automatyzacja procesu** w administracji systemem. Na tej stronie możesz zmodyfikować proces w tle, zmienić częstotliwość i zdefiniować okres snu.

Aby uzyskać więcej informacji na temat konfiguracji automatyzacji procesów, należy zapoznać się z tematem [Automatyzacja procesu](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

