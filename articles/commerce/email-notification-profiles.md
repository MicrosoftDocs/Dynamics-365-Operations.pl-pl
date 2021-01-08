---
title: Konfigurowanie powiadomień pocztą e-mail
description: W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4414854"
---
# <a name="set-up-an-email-notification-profile"></a>Konfigurowanie powiadomień pocztą e-mail


[!include [banner](includes/banner.md)]

W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Przed utworzeniem kanałów należy skonfigurować profil, aby zapewnić możliwość wysyłania powiadomień pocztą e-mail dla różnych zdarzeń, takich jak tworzenie zamówień, stan wysyłki zamówienia i niepowodzenia płatności.

Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Tworzenie powiadomień pocztą e-mail

Aby utworzyć profil powiadomień e-mail, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. W okienku akcji kliknij **Nowy**.
1. W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.
1. W polu **Opis** wprowadź odpowiedni opis.
1. Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.

### <a name="create-an-email-template"></a>Tworzenie szablonu wiadomości e-mail

Aby można było utworzyć powiadomienie e-mail, należy utworzyć szablon wiadomości e-mail organizacji zawierający informacje o adresach e-mail nadawców oraz szablon wiadomości e-mail.

Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Parametry sieci sprzedaży \> Szablony e-maili organizacji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Identyfikator e-mail** wprowadź identyfikator ułatwiający identyfikację tego szablonu.
1. W polu **Nazwa wysyłającego** wprowadź nazwę wysyłającego.
1. W polu **Opis e-maila** wprowadź odpowiedni opis.
1. W polu **Adres e-mail nadawcy** wprowadź adres e-mail nadawcy.
1. W sekcji **Ogólne** wprowadź wymagane informacje opcjonalne (takie jak priorytet wiadomości e-mail).
1. Rozwiń sekcję **Treść wiadomości E-mail** i wybierz opcję **Nowy**, aby utworzyć zawartość szablonu. Dla każdego elementu zawartości wybierz język i podaj wiersz tematu wiadomości e-mail. Jeśli wiadomość e-mail będzie zawierała treść, upewnij się, że pole **Zawiera treść** jest zaznaczone.
1. W okienku akcji wybierz **Wiadomość e-mail**, aby podać szablon treści wiadomości e-mail.

Na poniższym obrazie przedstawiono przykładowe ustawienia szablonów wiadomości e-mail.

![Ustawienia szablonu wiadomości e-mail](media/email-template.png)

### <a name="create-an-email-event"></a>Tworzenie wydarzenia e-mail

Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. Na liście znajdź i zaznacz odpowiedni rekord. 
1. Wybierz szablon wiadomości e-mail z listy rozwijanej **Identyfikator e-mail**.
1. Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.
1. Zaznacz pole wyboru **Aktywne**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.

![Ustawienia powiadomień wydarzeń](media/email-notification-profile.png)

### <a name="next-steps"></a>Następne kroki

Aby można było wysyłać wiadomości, należy skonfigurować usługę poczty wychodzącej i skonfigurować zadanie wsadowe. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
