---
title: Konfigurowanie profilu powiadomienia e-mail
description: W tym artykule opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: db6c46d471e3b54982132df3e4819236833cf4a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292143"
---
# <a name="set-up-an-email-notification-profile"></a>Konfigurowanie profilu powiadomienia e-mail

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób notyfikacji przez e-mail w rozwiązaniu Microsoft Dynamics 365 Commerce.

Podczas tworzenia kanałów można skonfigurować profil powiadomienia pocztą e-mail. Profil powiadomień e-mailowych definiuje zdarzenia transakcji sprzedaży (takie jak utworzone zamówienie, zamówienie spakowane i zamówienie zafakturowane), dla których będziesz wysyłać powiadomienia do swoich klientów. 

Aby uzyskać więcej informacji o sposobie konfigurowania poczty e-mail, zobacz [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).



## <a name="create-an-email-template"></a>Tworzenie szablonu wiadomości e-mail

Aby można było włączyć typ powiadomienia pocztą e-mail, należy utworzyć szablon wiadomości e-mail organizacji w programie Commerce Headquarters dla każdego typu powiadomienia, które chcesz obsługiwać. Ten szablon definiuje temat wiadomości e-mail, nadawcę, domyślny język i treść wiadomości e-mail dla każdego obsługiwanego języka.

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

Aby uzyskać informacje na temat tworzenia szablonów wiadomości e-mail, należy zapoznać się z tematem [Tworzenie szablonów wiadomości e-mail dla zdarzeń transakcyjnych](email-templates-transactions.md). 

## <a name="create-an-email-notification-profile"></a>Tworzenie powiadomień pocztą e-mail

Aby utworzyć profil powiadomień e-mail w headquarters, wykonaj następujące kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. W okienku akcji wybierz opcję **Nowy**.
1. W polu **Profil powiadomień e-mai** wprowadź nazwę identyfikującą profil.
1. W polu **Opis** wprowadź odpowiedni opis.
1. Umożliwia ustawienie **Aktywnego** przełącznika na **Tak**.

## <a name="add-a-notification-type"></a>Dodaj typ powiadomień

Aby utworzyć wydarzenie e-mail, należy wykonać poniższe kroki.

1. W okienku nawigacji kliknij kolejno opcje **Moduły \> Handel detaliczny i inny \> Ustawienia Headquarters \> Profil powiadomienia pocztą e-mail w Commerce**.
1. W obszarze **Ustawienia powiadomień pocztą e-mail dla sieci sprzedaży** wybierz pozycję **Nowy**.
1. Wybierz odpowiedni typ **Powiadomienia e-mail** z listy rozwijanej.
1. Wybierz szablon wiadomości e-mail utworzony powyżej z listy **rozwijanej Identyfikator wiadomości e-mail**.
1. Zaznacz pole wyboru **Aktywne**.
1. Na okienku akcji wybierz opcję **Zapisz**.

Na poniższym obrazie przedstawiono przykładowe ustawienia powiadomień e-mail wydarzeń.

![Ustawienia powiadomień wydarzeń.](media/email-notification-profile.png)


## <a name="schedule-a-recurring-email-notification-process-job"></a>Planowanie cyklicznego zadania przetwarzania powiadomień pocztą e-mail

Aby wysłać powiadomienia pocztą e-mail, musisz mieć uruchomione **zadanie przetwarzania powiadomień pocztą e-mail** dla zamówienia sieci sprzedaży.

Aby skonfigurować w centrali zadanie wsadowe wysyłania transakcyjnych wiadomości e-mail, należy wykonać następujące kroki.

1. Umożliwia przejście do modułu **Retail i Commerce \> Retail i Commerce — składniki IT \> E-mail i powiadomienia \> Wyślij powiadomienie e-mail**.
1. W oknie **dialogowym Przetwarzania powiadomień pocztą e-mail** dla zamówienia sieci sprzedaży wybierz opcję **Powtarzaj**.
1. W oknie dialogowym **Zdefiniuj cykliczność** wybierz **Brak daty końcowej**.
1. W **obszarze Wzorzec cyklu** wybierz opcję **Minuty**, a następnie **w polu Liczba** ustaw wartość **1**. Te ustawienia zapewniają przetwarzanie powiadomień pocztą e-mail tak szybko, jak to możliwe.
1. Wybierz **OK**, aby wrócić do okna dialogowego **Przetwarzaj powiadomienia e-mail o zamówieniach detalicznych**.
1. Naciśnij przycisk **OK**, aby zakończyć konfigurację zadania.

## <a name="next-steps"></a>Następne kroki

Aby można było wysyłać wiadomości, należy skonfigurować usługę poczty wychodzącej. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie i wysyłanie wiadomości e-mail](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Omówienie kanałów](channels-overview.md)

[Wymagania wstępne konfiguracji kanałów](channels-prerequisites.md)

[Omówienie organizacji i hierarchii organizacyjnych](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
