---
title: Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy
description: W tym artykule opisano sposób konfigurowania niestandardowych szablonów wiadomości e-mail dla określonych typów powiadomień i metod dostawy w firmie Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: f16bc23e3527f57bd61d73e92506946067c6eeb9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850311"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób konfigurowania niestandardowych szablonów wiadomości e-mail dla określonych typów powiadomień i metod dostawy w firmie Microsoft Dynamics 365 Commerce.

Można teraz dostosować wiadomości transakcyjne, aby utworzyć kombinację typu powiadomienia (np. **utworzone zamówienie**, **zapakowane** lub **zafakturowane zamówienie**) oraz metody dostawy (np. na następny dzień, odbiór w sklepie lub odbiór spod domu). Niestandardowe wiadomości transakcyjne umożliwiają detalistom dostarczanie ich klientom zamówień na realizację, które są dostosowane do metody dostawy zamówienia. Na przykład zdarzenie „zapakowanie zapakowane” może być dostosowywane w taki sposób, aby dostarcza klientom Curbside instrukcje dotyczące odbioru, którzy wybierają Curbside pobrania. Można również udostępnić informacje o firmie przewozowej i dostawie dla odbiorców, którzy wybierają zamówienie wysyłki.

> [!NOTE]
> Aby skorzystać z funkcji niestandardowych transakcyjnych wiadomości e-mail, należy najpierw włączyć **funkcję zarządzania szablonami transakcyjnych wiadomości e-mail według metod dostawy** przechodząc do **obszaru obszary robocze \> w module** Commerce Headquarters.

Wiadomości e-mail można dostosowywać za pomocą metody dostawy dla następujących typów powiadomień:

- **Anulowanie zamówienia** — ten typ powiadomienia e-mail jest nowy.
- **Zamówienie utworzone**
- **Zamówienie potwierdzone**
- **Zamówienie zafakturowane** — ten typ powiadomienia e-mail jest nowy. Można go użyć zamiast **typu powiadomienia o wysyłce zamówienia**, który wyśle powiadomienie dla dowolnego zdarzenia faktury, które ma metodę dostawy (a nie odbiór, wysyłka lub elektroniczna metoda dostawy).
- **Zamówienie pobrane**
- **Zamówienie spakowane**
- **Zamówienie gotowe do pobrania** — ten typ powiadomienia można dostosować za pomocą metody dostawy tylko **w przypadku włączenia obsługi wielu metod dostawy**. W takim przypadku ten typ powiadomienia jest funkcjonalnie równoważny **typowi zapakowanego** powiadomienia zamówienia.
- **Płatność nie powiodła się**
- **Zamówienie wymiany utworzone**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Konfigurowanie szablonów wiadomości e-mail dla konkretnych metod dostawy

W przypadku tej procedury przyjęto założenie, że utworzono już nowe, niestandardowe szablony wiadomości e-mail i dodano je do **strony szablony wiadomości e-mail organizacji**. Aby uzyskać informacje na temat tworzenia i przekazywania szablonów wiadomości e-mail, należy zapoznać się z tematem [Tworzenie szablonów wiadomości e-mail dla zdarzeń transakcyjnych ](email-templates-transactions.md).

Aby skonfigurować szablony wiadomości e-mail dla konkretnych metod dostawy w programie Commerce Central, należy wykonać następujące kroki.

1. Przejdź do **profilu powiadomień e-mail w portalu Commerce**.
1. W obszarze **Ustawienia powiadamiania o zdarzeniach sieci sprzedaży** Wybierz istniejący typ powiadomienia.
1. Gdy typ powiadomienia jest wciąż wybrany, wybierz opcję **Konfiguruj metody dostawy**.
1. Na stronie **Metody dostawy** wybierz opcję **Nowa**.
1. W polu **Metoda dostawy** wybierz metodę dostawy do skojarzenia z tym profilem.
1. W **polu Identyfikator wiadomości e-mail** wybierz szablon wiadomości e-mail, który ma zostać zamapowany do metody dostawy.
1. Zaznacz pole wyboru **Aktywne**.
1. Powtórz kroki od 4 do 7, aby dodać kolejne metody dostawy.
1. Po zakończeniu wybierz przycisk **OK**.

> [!NOTE]
> - Jeśli w wierszach zamówienia sprzedaży znajduje się więcej niż jeden tryb dostawy, zostanie użyty szablon domyślny. Szablon domyślny jest mapowany na typ powiadomienia na **stronie profil powiadomień pocztą e-mail w module Commerce**.
> - Jeśli zamówienie sprzedaży ma tryb dostawy, który nie został skonfigurowany dla niestandardowego szablonu wiadomości e-mail, zostanie użyty domyślny szablon wiadomości e-mail.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Tworzenie zamówień w biurach obsługi](tasks/create-call-center-orders.md)

[Zmienianie metody dostawy w punkcie sprzedaży](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]