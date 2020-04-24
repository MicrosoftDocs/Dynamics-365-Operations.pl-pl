---
title: Komunikaty akcji
description: Komunikat akcji jest generowaną przez system sugestią dotyczącą zmiany istniejącego zamówienia planowanego lub zaakceptowanego.
author: ChristianRytt
manager: tfehr
ms.date: 10/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6eb65f0cf97490177d38001e5ac793aa584f33bb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203970"
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





