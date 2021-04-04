---
title: Ustawienia dostawcy dodane dla kosztu z wyładunkiem
description: W tym temacie opisano nowe pola, które są dodawane do istniejącej strony Dostawcy po włączeniu modułu Koszt z wyładunkiem. Za pomocą tych pól można skonfigurować dostawców, których będzie można używać wraz z funkcjami Koszty z wyładunkiem.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8cc0622cd761a671ebb88addc36b777cfefb7dc7
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500917"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Ustawienia dostawcy dodane dla kosztu z wyładunkiem

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Po włączeniu modułu **Koszt z wyładunkiem** do istniejącej strony **Dostawcy** zostanie dodanych kilka nowych pól. Za pomocą tych pól można skonfigurować dostawców, których będzie można używać wraz z funkcjami Koszty z wyładunkiem.

Aby ustawić odpowiednie pola, przejdź do **Zaopatrzenie i sourcing \> Dostawcy \> Wszyscy dostawcy**. Otwórz istniejącego dostawcę lub utwórz nowego dostawcę, a następnie wybierz skróconą kartę **Dodatkowe szczegóły**. Wszystkie nowe pola, które są dodaje moduł **Koszty z wyładunkiem**, są wyświetlane pod nagłówkiem **Podróży**. W poniższej tabeli opisano dostępne pola.

| Pole | opis |
|---|---|
| Typ wysyłki | <p>Umożliwia wybór roli dostawcy w odniesieniu do kosztu z wyładunkiem:</p><ul><li>**Brak** — dostawca nie ma określonej roli związanej z kosztem z wyładunkiem. Jest to ustawienie domyślne, ponieważ większość dostawców prawdopodobnie nie ma określonej roli.</li><li>**Firma przewozowa** — dostawcą jest firma przewozowa. Dostawcy z takim typem wysyłki są dostęp do wyboru w polu **Firma przewozowa** na stronie **Podróży**.</li><li>**Broker celny** — dostawca jest brokerem celnym. Dostawcy z takim typem wysyłki są dostęp do wyboru w polu **Broker celny** na stronie **Folio**.</li><li>**Agent** — dostawca jest agentem. Dostawcy z takim typem wysyłki są dostęp do wyboru w polu **Agent** na stronach **Dostawcy** i **Zamówienia zakupu**.</li></ul> |
| Grupa typów kosztów | Przypisz dostawcę do grupy typów kosztów w celu wybrania [kosztów automatycznych](auto-cost-setup.md). |
| Port źródłowy | Wybierz port pochodzenia podróży. |
| Agent | Domyślny agent dla zakupów u dostawcy. |
| Dostawca wyceny importu | <p>Wskaż, czy dostawca jest dostawcą kosztów z wyładunkiem.</p><p>**Porada:** Tego pola można używać razem z zabezpieczeniami na poziomie rekordu, aby ograniczyć zamówienia zakupu wyświetlane podczas tworzenia podróży.</p> |
| Firma przewozowa | Umożliwia wybór domyślnej firmy przewozowej używanej podczas tworzenia zamówień zakupu dla dostawcy. |
| Dostawca usług | Wskaż, czy dostawca jest dostawcą usług. |
| Grupa tolerancji nadwyżki/niedoboru | Umożliwia wybór domyślnej grupy tolerancji nadwyżki/niedoboru dla dostawcy. |
