---
title: Sprawdzanie stanu eksperymentu
description: W tym temacie wyjaśniono, jaki stan ma eksperyment w cyklu życia eksperymentu w systemie Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: eea67ddc1718902198b74614ee1a910fc6e29c1d
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/22/2020
ms.locfileid: "4415082"
---
# <a name="review-the-status-of-an-experiment"></a>Sprawdzanie stanu eksperymentu
Jest wiele kroków związanych z konfigurowaniem i uruchamianiem eksperymentu w systemie Dynamics 365 Commerce. Aby uzyskać informacje na temat cyklu życia eksperymentu, zobacz temat [Eksperymentowanie w systemie Dynamics 365 Commerce](experimentation-overview.md).

Aby dowiedzieć się, gdzie eksperyment znajduje się w cyklu życia, w konstruktorze witryn Commerce wybierz **Eksperymenty** w okienku nawigacji po lewej stronie. Zostanie wyświetlona lista eksperymentów ze stanem każdego eksperymentu w module Commerce i w ramach usługi innej firmy, która jest używana do tworzenia eksperymentów, przypisywania odmian i analizowania danych.

W kolumnie **Stan Commerce** mogą być wyświetlane następujące wartości: 
- **Wersja robocza** — eksperyment jest połączony ze stroną lub fragmentem w Commerce i jest edytowany.
- **Opublikowany** — warianty eksperymentów są gotowe do wyświetlenia w witrynie internetowej. Jeśli eksperyment jest uruchomiony w usłudze innej firmy, użytkownicy witryny sieci Web będą widzieli odmianę strony lub fragmentu jako wybraną przez usługę innej firmy.
- **Wycofany** — eksperyment nie jest już dostępny w serwisie WWW. Użytkownicy witryny sieci Web będą widzieli tylko odmianę strony lub fragmentu jako wybraną przez usługę innej firmy nawet jeśli eksperyment jest uruchomiony w usłudze innej firmy.
- **Zakończony** — eksperyment został przeprowadzony, a odmiana została przeniesiony do eksploatacji dla wszystkich użytkowników witryny sieci Web.

Podobnie, w kolumnie **stanu firmy zewnętrznej** można wyświetlić następujące wartości wskazujące stan eksperymentów w usłudze innej firmy.
- **Wersja robocza** — eksperyment jest konfigurowany w usłudze innej firmy, ale nie został uruchomiony.
- **Uruchomiony** — eksperyment został uruchomiony w usłudze innej firmy i gromadzi dane.
- **Wstrzymany** — eksperyment jest wstrzymany i nie zbiera danych. Aby ponownie zebrać dane, musisz wznowić eksperyment.
- **Zarchiwizowany** — eksperyment został przeprowadzony i skatalogowany w usłudze innej firmy do użytku w przyszłości.

Poniższy diagram przedstawia oba zestawy stanów oraz sposób ich powiązania.

[ ![Stany eksperymentów](./media/experimentation_statuses.svg) ](./media/experimentation_statuses.svg#lightbox)


[!INCLUDE[footer-include](../includes/footer-banner.md)]