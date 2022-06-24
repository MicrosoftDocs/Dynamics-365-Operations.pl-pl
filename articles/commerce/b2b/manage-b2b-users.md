---
title: Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B
description: W tym artykule opisano, jak dodawać, usuwać i edytować użytkowników partnerów biznesowych w witrynach e-commerce Microsoft Dynamics 365 Commerce typu business-to-business (B2B) oraz w centrali Commerce headquarters.
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4a3d1c7bf7e7ea545590315d9e185fa525b5d5e3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860302"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B

[!include [banner](../../includes/banner.md)]

W tym artykule opisano, jak dodawać, usuwać i edytować użytkowników partnerów biznesowych w witrynach e-commerce Microsoft Dynamics 365 Commerce typu business-to-business (B2B) oraz w centrali Commerce headquarters.

> [!NOTE]
> - Warunkiem [wstępnym tego dokumentu jest artykuł Zarządzanie partnerami biznesowymi b2B przy użyciu hierarchii](partners-customer-hierarchies.md) klientów.
> - Upewnij się, że zainicjowałeś encję Typy dokumentów w centrali Commerce, otwierając formularz **Typy dokumentów** w zakładce **Administracja organizacji \> Zarządzanie dokumentami \> Typy dokumentów**.

Witryny handlu elektronicznego B2B wymagają od organizacji rejestracji, aby zostać partnerami biznesowymi. Po przesłaniu przez organizację danych rejestracyjnych do witryny handlu elektronicznego B2B żądanie rejestracji przechodzi proces kwalifikacji. Jeśli organizacja zostanie pomyślnie zakwalifikowana, zostaje przyjęta jako partner biznesowy.

Po dołączeniu organizacji jako partnera biznesowego użytkownik organizacji, który zainicjował wniosek o zostanie partnerem biznesowym, jest identyfikowany jako użytkownik administratora i otrzymuje uprawnienia do dołączania dodatkowych autoryzowanych użytkowników witryny handlu elektronicznego B2B. Następnie ci autoryzowani użytkownicy mogą składać zamówienia w imieniu partnera biznesowego.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Konfigurowanie użytkownika administratora dla nowego partnera biznesowego

Potencjalni partnerzy biznesowi mogą zainicjować proces wprowadzania do witryny e-commerce B2B, przesyłając żądanie włączenia za pośrednictwem łącza na stronie B2B. Następnie mogą użyć dostosowywalnych formularzy, aby podać szczegóły wymagane do przysłania i rejestracji. Po przesłaniu żądania zostanie wyświetlona strona potwierdzenia przesłania. Jeśli zgłoszenie zostanie zatwierdzone, firma, dla której przekazano wniosek, staje się partnerem biznesowym, a osoba zgłaszająca żądanie (użytkownik, który zainicjował wniosek o włączenie) staje się administratorem partnera biznesowego.

Aby zatwierdzić prośbę o partner biznesowy w centrali handlowej, wykonaj następujące kroki.

1. Wybierz **Handel detaliczny i inny Dane IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **P-0001**, aby ściągnąć wszystkich partnerów biznesowych przy dołączaniu żądań do centrali w programie Commerce Headquarters.
1. Po pomyślnym uruchomieniu zadania **P-0001** przejdź do **Retail i Commerce IT \> Odbiorca** oraz uruchom zadanie **Synchronizuj klientów i prośby o kanał**. Po pomyślnym wykonaniu tego zadania żądania włączenia są tworzone jako prospekty typu **prospekt B2B** w centrali handlowej. 
1. Przejdź do **Klienci \> Wszyscy potencjalni klienci** i wybierz rekord nowego partnera biznesowego, aby otworzyć stronę szczegółów potencjalnych klientów.
1. Na karcie **Ogólne** wybierz pozycję **Konwertuj \> Zatwierdź/odrzuć**, aby zatwierdzić wniosek o przyjęcie. Gdy pojawi się komunikat potwierdzenia, potwierdź, że chcesz kontynuować proces, i zatwierdź żądanie. Zatwierdzenie zmienia pole **Stan** rekordu prospektu jest ustawiana wartość **Zatwierdzone**. Następnie na adres e-mail wnioskutora zostanie wysłana wiadomość e-mail w celu potwierdzenia, że ich organizacja została zatwierdzona jako partner biznesowy. Zostanie również utworzona hierarchia odbiorcy, w której klient jest dodawany jako administrator partnera biznesowego.

    > [!NOTE]
    > Obecnie wiadomość e-mail z potwierdzeniem jest wysyłana natychmiast po zatwierdzeniu. Przyszłe funkcje commerce pozwalają jednak administratorowi ręcznie wyzwalać wiadomości e-mail.

1. Przejdź do **Retail i Commerce IT \> Harmonogram dystrybucji** i uruchom zadanie **1010 (Odbiorcy)**, aby przesunąć nowe rekordy hierarchii odbiorców i odbiorców do bazy danych kanału.

> [!NOTE]
> Aby upewnić się, że nowe rekordy klientów są wysyłane do bazy danych kanału, co najmniej jedna z książek adresowych powiązanych z klientem powinna być uwzględniona w książce adresowej klienta powiązanej ze sklepem internetowym. Ten proces można zautomatyzować, konfigurując książkę adresową domyślnego odbiorcy sklepu internetowego, aby system skopiował wartość książki adresowej do każdego nowego odbiorcy.

Po zsynchronizowaniu rekordów hierarchii klientów z bazą danych kanału osoba żądająca może zalogować się do witryny handlu elektronicznego B2B przy użyciu adresu e-mail podanego podczas przesyłania żądania włączenia. Użytkownicy mogą używać przepływu rejestracji w celu zdefiniowania hasła dla swojego konta. Aby uzyskać informacje o tym, jak włączyć rekord dostawcy tożsamości usługi Azure Active Directory (Azure AD) B2C, który ma być połączony z rekordem klienta B2B, który został utworzony po zatwierdzeniu potencjalnego klienta, zobacz [Włączanie automatycznego łączenia](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Powiadamiaj prospekty B2B o ich zatwierdzeniu lub odrzuceniu

Gdy zatwierdzisz lub odrzucisz prośbę o włączenie do potencjalnego klienta B2B, do potencjalnego klienta może zostać automatycznie wysłane powiadomienie e-mailem.

Aby skonfigurować powiadomienia pocztą e-mail w centrali Commerce dla zdarzeń typu powiadomień **zatwierdzenia prospektu B2B** lub **odrzucenia prospektu B2B**, należy wykonać następujące kroki.

1. Twórz szablony wiadomości e-mail dla wiadomości e-mail, które będą wysyłane do potencjalnych klientów, gdy typ powiadomienia **zatwierdzony prospekt B2B** lub **prospekt B2B odrzucony** jest Aby uzyskać informacje o symbolach zastępczych, zobacz temat [Typy powiadomień](../email-templates-transactions.md#notification-types). Aby uzyskać informacje dotyczące sposobu tworzenia szablonów wiadomości e-mail, zobacz temat [Tworzenie szablonu wiadomości e-mail](../email-templates-transactions.md#create-an-email-template).
1. Dodaj typy **powiadomień zatwierdzenia** i **odrzucenia prospektu B2B** do profilu powiadomień poczty e-mail i mapuje je na utworzone szablony wiadomości e-mail. Więcej informacji na temat profili powiadomień jest dostępnych w artykule [Konfigurowanie profilu powiadomienia](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Dodatkowi użytkownicy partnera biznesowego

Użytkownik administrator partnera biznesowego może w razie potrzeby do witryny sieci web B2B handlu elektronicznego dołączać dodatkowych użytkowników partnerów biznesowych.

Aby do witryny sieci web B2B handlu elektronicznego do pracy dołączać dodatkowych użytkowników partnerów biznesowych, należy wykonać następujące kroki.

1. Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
1. Przejdź do **Moje konto \> Użytkownicy orgznizacji \> Wyświetl szczegóły** i wybierz **Dodaj użytkownika**.
1. Wprowadź wymagane informacje, a następnie wybierz przycisk **Zapisz**. W polu stan nowego użytkownika jest ustawiona wartość **Oczekująca**.

Po uruchomieniu zadań **P-0001** i **Synchronizuj klientów i żądania kanałów** tworzony jest rekord klienta typu **Osoba** dla nowego użytkownika w centrali handlowej. Ten rekord odbiorcy jest również skojarzony z rekordem hierarchii odbiorcy odpowiedniego partnera biznesowego. Ponadto na adres e-mail nowego użytkownika wysyłana jest wiadomość e-mail z powiadomieniem, że został on dodany jako użytkownik organizacji partnera biznesowego i może teraz zalogować się do witryny handlu elektronicznego B2B.

Uruchom zadanie **1010 (Odbiorcy)**, aby zsynchronizować nowego użytkownika partnera biznesowego z bazą danych kanału sprzedaży.

Po zsynchronizowaniu rekordu odbiorcy stan użytkownika w witrynie B2B handlu elektronicznego jest ustawiany na **Aktywny**, a nowy użytkownik może zalogować się do witryny B2B handlu elektronicznego, używając swojego adresu e-mail. Użytkownicy mogą używać przepływu rejestracji w celu zdefiniowania hasła dla swojego konta. Aby uzyskać informacje o tym, jak włączyć rekord dostawcy tożsamości usługi Azure AD B2C, który ma być połączony z rekordem klienta B2B, który został utworzony po zatwierdzeniu potencjalnego klienta, zobacz [Włączanie automatycznego łączenia](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Edytowanie szczegółów użytkownika-partnera biznesowego

Aby edytować szczegóły użytkowników partnerów biznesowych, wykonaj poniższe kroki.

1. Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
1. Przejdź do **Moje konto \> Użytkownicy organizacji \> Wyświetl szczegóły**, wybierz przycisk **Edytuj** (symbol symbolu myszy), dokonaj wymaganych zmian, a następnie wybierz pozycję **Zapisz**. Zmiany zaczną obowiązywać dopiero po uruchomieniu zadań **P-0001**, **Synchronizuj klientów i żądania kanałów** oraz **1010 (Klienci)**.

## <a name="remove-a-business-partner-user"></a>Usuń użytkownika partnera biznesowego

W razie potrzeby administrator może usunąć istniejących użytkowników organizacji partnera biznesowego z listy użytkowników, którzy mają dostęp do witryny sieci web B2B handlu elektronicznego.
Aby usunąć użytkownika partnera biznesowego, wykonaj następujące kroki.
- Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
- Przejdź do **Moje konto > Użytkownicy orgznizacji \> Wyświetl szczegóły** i wybierz przycisk **Usuń** (symbol X). Gdy pojawi się komunikat zatwierdzenia, potwierdź, że chcesz usunąć użytkownika. Zmiany zaczną obowiązywać dopiero po uruchomieniu zadań **P-0001**, **Synchronizuj klientów i żądania kanałów** oraz **1010 (Klienci)**.

> [!NOTE]
> Usunięcie użytkownika z listy użytkowników, którzy mogą uzyskać dostęp do witryny sieci web B2B handlu elektronicznego, spowoduje usunięcie odpowiedniego rekordu odbiorcy z rekordu hierarchii odbiorcy partnera biznesowego. Jednak sam rekord odbiorcy nie został usunięty z Commerce headquarters.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Dołączanie istniejących odbiorców jako partnerów biznesowych w witrynie sieci web B2B e-commerce

Administratorzy mogą dołączać partnerów biznesowych i użytkowników bezpośrednio w programie Commerce Headquarters. Ta możliwość jest przydatna przy dołączaniu istniejących partnerów biznesowych do witryny sieci web B2B e-commerce.

Aby dołączyć partnerów biznesowych i użytkowników w centrali Commerce, wykonaj następujące kroki.

1. Utwórz lub wybierz klienta typu **Organizacja**, którego chcesz dodać jako partnera biznesowego.
1. Utwórz lub wybierz klienta typu **Osoba**, aby dodać go jako administratora lub użytkownika dla partnera biznesowego. Upewnij się, że główne adresy e-mail są skojarzone z klientami. Te adresy e-mail są używane do logowania się do witryny sieci web. 

    > [!NOTE]
    > System musi mieć możliwość znalezienia unikatowego rekordu odbiorcy dla użytkowników, którzy powinni mieć możliwość logowania się do witryny sieci web. Jeśli w firmie system znajdzie więcej niż jednego klienta, który ma ten sam podstawowy adres e-mail, użytkownik nie będzie mógł zalogować się do witryny sieci web.

1. Utwórz identyfikator hierarchii odbiorcy.
1. W polu **Nazwa** wprowadź nazwę.
1. W polu **Organizacja** wpisz partnera biznesowego organizacji klienta.
1. Na skróconej karcie **Hierarchia** wybierz pozycję **Dodaj**.
1. W polu **Nazwa** wybierz klienta typu **Osoba**.
1. Wybierz rolę **Administrator** dla odbiorcy, który powinien być wyznaczony jako administrator.
1. Powtórz ten proces, aby dodać dodatkowych odbiorców do hierarchii.

## <a name="additional-information"></a>Informacje dodatkowe

- Wszystkie zadania wymienione w tym artykule można skonfigurować do uruchamiania zgodnie z harmonogramem w formacie wsadowym. Oczekiwania jest takie, że partnerzy biznesowi konfigurują w razie potrzeby zadania wsadowe.
- Obecnie tylko jeden rekord użytkownika / klienta można wyznaczyć jako użytkownika administratora, a tę rolę można zmienić tylko w centrali Commerce. Nie ma wsparcia dla funkcji samoobsługi, które pozwalają partnerom biznesowym na wyznaczanie wielu administratorów lub zmianę administratorów w witrynach handlu elektronicznego B2B.
- Chociaż można zdefiniować limity wydatków dla użytkowników, wymuszanie limitów wydatków podczas procesu wprowadzania zamówienia nie zostało jeszcze wdrożone.
- Cała logika biznesowa i sprawdzanie poprawności działania użytkownika w witrynie handlu elektronicznego B2B są oparte na konfiguracji rekordu klienta, który jest mapowany na użytkownika w siedzibie firmy Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny wykorzystywanej na potrzeby handlu elektronicznego B2B](set-up-b2b-site.md)

[Zarządzanie partnerami biznesowymi B2B przy użyciu hierarchii klientów](partners-customer-hierarchies.md)

[Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B](payment-method.md)

[Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego](quantity-limits.md)

[Omówienie sekwencji identyfikatorów](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
