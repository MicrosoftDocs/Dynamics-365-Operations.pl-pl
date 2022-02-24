---
title: Przenieś podksięgę do księgi głównej
description: W tym temacie opisano możliwości rozwiązania Microsoft Dynamics 365 Finance związane z procesem przenoszenia księgi podrzędnej w księdze głównej.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: 7addb1f26a33db84d947e6fede876be648d2c654
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645177"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Przenieś podksięgę do księgi głównej

[!include [banner](../includes/banner.md)]

W tym temacie opisano możliwości rozwiązania Microsoft Dynamics 365 Finance, które są związane z regułami przenoszenia partii zapisów w arkuszu księgi podrzędnej.

W wersji 8.1 wprowadzono zmiany umożliwiające przeniesienie reguł, które nie wykluczają opcji **Synchronicznie**. Aby uzyskać więcej informacji, zobacz [Usunięte i przestarzałe funkcje w Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

Dostępne są następujące opcje przenoszenia partii w księdze podrzędnej. 

 - Asynchroniczne — ta opcja powoduje natychmiastowe zaplanowanie przenoszenia zapisów księgowych księgi podrzędnej do księgi głównej. Załącznik księgi głównej zostanie zarejestrowany, gdy tylko zasoby będą wolne do przetworzenia tego żądania na serwerze. 

- Zaplanowana partia — ta opcja spowoduje dodanie zapisów księgowych z księgi, które są przenoszone do kolejki przetwarzania w księdze głównej, gdzie zapisy będą przetwarzane w zleceniu otrzymanym. Załącznik księgi głównej zostanie zarejestrowany o określonym czasie, gdy tylko zasoby będą wolne do przetworzenia tego zadania wsadowego na serwerze. 
 
W wersji 10.0.8 dokonano ulepszeń w celu zwiększenia wydajności opcji asynchronicznej. Ta funkcja jest włączana pod nazwą **optymalizacji wydajności transferu podksięgi do księgi głównej**. 
 
Ta funkcja poprawia przeniesienie danych z księgi podrzędnej do księgi głównej. Dzięki temu proces jest bardziej wydajny i grupuje w nim zestawy mniejszych transakcji do przeniesienia. Pozwala to na wydajniejsze korzystanie z serwera przetwarzania wsadowego. Ta funkcja wymaga skonfigurowania serwera przetwarzania wsadowego, trybu online i działania, aby można było korzystać z opcji transferu asynchronicznego. 
