---
title: Konfigurowanie powiadomień pocztą e-mail
description: W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ac58ea4f1dfd8208c1c2f78e36d82d1375475413
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349527"
---
# <a name="set-up-an-email-notification-profile"></a>Konfigurowanie profilu powiadomienia

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.

Podczas tworzenia kanałów można skonfigurować profil powiadomienia pocztą e-mail. W ten sposób wiadomości e-mail mogą być wysyłane do odbiorców w związku z różnymi zdarzeniami transakcyjnmi, takimi jak tworzenie zamówienia, stan wysyłki zamówienia czy niepowodzenie płatności.

Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Tworzenie powiadomień pocztą e-mail

Aby utworzyć profil powiadomień e-mail, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. W okienku akcji kliknij **Nowy**.
1. W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.
1. W polu **Opis** wprowadź odpowiedni opis.
1. Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.

### <a name="create-an-email-template"></a>Tworzenie szablonu wiadomości e-mail

Aby można było włączyć typ powiadomienia pocztą e-mail, należy utworzyć szablon wiadomości e-mail organizacji w programie Commerce Headquarters. Ten szablon definiuje temat wiadomości e-mail, nadawcę, domyślny język i treść wiadomości e-mail dla każdego języka, który ma być używany.

Aby utworzyć szablon wiadomości e-mail, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Parametry sieci sprzedaży \> Szablony e-maili organizacji**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Identyfikator e-mail** wprowadź identyfikator ułatwiający identyfikację tego szablonu.
1. W polu **Nazwa wysyłającego** wprowadź nazwę wysyłającego.
1. W polu **Opis e-maila** wprowadź odpowiedni opis.
1. W polu **Adres e-mail nadawcy** wprowadź adres e-mail nadawcy.
1. W sekcji **Ogólne** wybierz domyślny język szablonu wiadomości e-mail. Domyślny język będzie używany, gdy dla określonego języka nie istnieje żaden zlokalizowany szablon.
1. Rozwiń sekcję **Treść wiadomości E-mail** i wybierz opcję **Nowy**, aby utworzyć zawartość szablonu. Dla każdego elementu zawartości wybierz język i podaj wiersz tematu wiadomości e-mail. Jeśli wiadomość e-mail będzie zawierała treść, upewnij się, że pole **Zawiera treść** jest zaznaczone.
1. W okienku akcji wybierz **Wiadomość e-mail**, aby podać szablon treści wiadomości e-mail.

Na poniższym obrazie przedstawiono przykładowe ustawienia szablonów wiadomości e-mail.

![Ustawienia szablonu wiadomości e-mail.](media/email-template.png)

### <a name="create-an-email-event"></a>Tworzenie wydarzenia e-mail

Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. Na liście znajdź i zaznacz odpowiedni rekord. 
1. Wybierz szablon wiadomości e-mail z listy rozwijanej **Identyfikator e-mail**.
1. Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.
1. Zaznacz pole wyboru **Aktywne**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.

![Ustawienia powiadomień wydarzeń.](media/email-notification-profile.png)

### <a name="next-steps"></a>Następne kroki

Aby można było wysyłać wiadomości, należy skonfigurować usługę poczty wychodzącej i skonfigurować zadanie wsadowe. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
