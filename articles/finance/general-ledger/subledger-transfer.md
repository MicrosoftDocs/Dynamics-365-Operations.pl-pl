---
title: Przenieś podksięgę do księgi głównej
description: W tym temacie opisano możliwości rozwiązania związane z procesem przenoszenia księgi podrzędnej w księdze głównej.
author: rcarlson
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: a2fdeaadc7453458f8fc7165664eccedee632f5f
ms.sourcegitcommit: e9cf75545d55bfb2f37b2036df886128879a5b73
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/21/2021
ms.locfileid: "6646807"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Przenieś podksięgę do księgi głównej

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości rozwiązania, które są związane z regułami przenoszenia partii zapisów w arkuszu księgi podrzędnej.

W wersji 8.1 wprowadzono zmiany umożliwiające przeniesienie reguł, które nie wykluczają opcji **Synchronicznie**. Aby uzyskać więcej informacji, zobacz [Usunięte i przestarzałe funkcje w Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Dostępne są następujące opcje przenoszenia partii w księdze podrzędnej:

- **Asynchroniczne** — Przeniesienie zapisów księgowych księgi podrzędnej do księgi głównej jest planowane natychmiast. Załącznik księgi głównej zostanie zarejestrowany, gdy tylko zasoby będą dostępne do przetworzenia tego żądania na serwerze.
- **Zaplanowane zadanie wsadowe** — Zapisy księgowe księgi podrzędnej, które muszą zostać przeniesione, są dodawane do kolejki przetwarzania w księdze głównej. Wpisy w kolejce będą przetwarzane w kolejności, w jakiej zostały odebrane. Każdy załącznik księgi głównej zaktualizuje konta w zaplanowanym czasie, jeśli dostępne są zasoby do przetwarzania zadania wsadowego na serwerze.

W wersji 10.0.8 dokonano ulepszeń w celu zwiększenia wydajności opcji **asynchronicznej**. Ta funkcja jest włączana pod nazwą **optymalizacji wydajności transferu podksięgi do księgi głównej**.

Funkcjonalność asynchronicznego przesyłania partii księgi podrzędnej pomaga usprawnić transfer danych z księgi podrzędnej do księgi głównej. Dzięki grupowaniu zestawów mniejszych transakcji i przenoszeniu transakcji w grupy, funkcjonalność efektywniej przetwarza transakcje. Podczas grupowania transakcji zasoby serwera przetwarzania wsadowego są używane efektywniej.

Asynchroniczny transfer partii księgi podrzędnej wymaga, aby serwer wsadowy był skonfigurowany, w trybie online i działał. W przeciwnym razie opcja transferu **asynchronicznego** nie działa.

Zmiana wydajności na poziomie partii używa jednego cyklicznego zadania wsadowego dla wszystkich firm w systemie. W czasie wykonywania tworzone jest nowe zadanie wsadowe w celu przetworzenia wymaganych rekordów, które nie zostały jeszcze przeniesione. Więcej ustawień można kontrolować za pomocą strony **Automatyzacja procesu** w administracji systemem. Na tej stronie możesz zmodyfikować proces w tle, zmienić częstotliwość i zdefiniować okres snu.

Aby uzyskać więcej informacji na temat konfiguracji automatyzacji procesów, należy zapoznać się z tematem [Automatyzacja procesu](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
