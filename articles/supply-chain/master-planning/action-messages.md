---
title: Komunikaty akcji
description: Komunikat akcji jest generowaną przez system sugestią dotyczącą zmiany istniejącego zamówienia planowanego lub zaakceptowanego.
author: ChristianRytt
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, MCRSalesOrderMessages, MCRSalesTableDetailedStatus, TAMItemVendRebateGroup, TAMVendRebate, TAMVendRebateAgreementLineInfoPart, TAMVendRebateGroup, TAMVendRebateTable, TAMVendRebateTrans, ReqTransActionListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb208d390d3b5d2091f5b0f112532794a4d78d8adcf947291a4183c3b3fd3f9c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769570"
---
# <a name="action-messages"></a>Komunikaty akcji

[!include [banner](../includes/banner.md)]

Komunikat akcji jest generowaną przez system sugestią dotyczącą zmiany istniejącego zamówienia planowanego lub zaakceptowanego.

## <a name="introduction"></a>Wprowadzenie

Komunikaty akcji są generowane przez obliczenia planowania głównego w odpowiedzi na zmianę wymagań. Na przykład, w zamówieniu sprzedaży, dla którego utworzono już zamówienie zakupu, może zostać zmieniona data wysyłki lub ilość. W takiej sytuacji obliczenia planowania głównego wygenerują jeden lub więcej komunikatów akcji w celu zaktualizowania zamówienia zakupu. Użytkownik decyduje, czy konieczne jest wprowadzenie sugerowanych zmian.

Istnieje możliwość konfiguracji sposobu obliczania komunikatów akcji dla grupy zapotrzebowania, którą można dołączyć do towaru.

## <a name="select-action-messages"></a>Wybieranie komunikatów akcji

Na stronie **grup zapotrzebowania** można wybrać komunikaty akcji, które mają być generowane przez system, oraz grupy lub elementy, których te komunikaty będą dotyczyć. Dostępne są następujące komunikaty akcji.

| Komunikat             | Opis                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Zaliczka**         | Jeśli wybierzesz ten komunikat, system wygeneruje komunikaty akcji, jeśli będzie taka potrzeba, aby przenieść zamówienia do wcześniejszej daty. W polu **Dop. opóźnienie** można również określić maksymalną liczbę dni między otrzymaniem a wydaniem bez podejmowania akcji. |
| **Opóźnij**        | Jeśli wybierzesz ten komunikat, system wygeneruje komunikaty akcji, jeśli będzie taka potrzeba, aby przenieść zamówienia do późniejszej daty. W polu **Dop. wyprzedzenie** można również określić maksymalną liczbę dni między otrzymaniem a wydaniem bez wyprzedzania.       |
| **Zmniejsz**        | Ta opcja pozwala określić, czy może być proponowane zmniejszenie zleceń produkcyjnych, zamówień zakupu lub innych transakcji przychodów w celu uniknięcia nadmiarów w zapasach.                                                                                                   |
| **Zwiększ**        | Ta opcja pozwala określić, czy może być proponowane zwiększenie zleceń produkcyjnych, zamówień zakupu lub innych transakcji przychodów w celu uniknięcia niedoborów w zapasach.                                                                                                    |
| **Akcje pochodne** | Wybranie tego komunikatu powoduje tworzenie komunikatów akcji dla zapotrzebowań pochodnych, np. tworzone są akcje dotyczące zamówień części koniecznych do produkcji.                                                                                                   |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]