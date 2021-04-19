---
title: Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B
description: W tym temacie opisano, w jaki sposób administratorzy mogą dodawać, edytować i usuwać użytkowników partnerów biznesowych w witrynach sieci Web handlu elektronicznego typu business-to-business (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7c1bd8d9cb494cef78fa7c14f6c391821d48749a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799860"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B

[!include [banner](../../includes/banner.md)]

W tym temacie opisano, w jaki sposób administratorzy mogą dodawać, edytować i usuwać użytkowników partnerów biznesowych w witrynach sieci Web handlu elektronicznego typu business-to-business (B2B).

Witryny handlu elektronicznego B2B wymagają od organizacji rejestracji, aby zostać partnerami biznesowymi. Po tym, jak organizacja prześle dane rejestracyjne do witryny handlu elektronicznego B2B, przechodzi przez proces kwalifikacji. Jeśli organizacja zostanie pomyślnie zakwalifikowana, zostaje przyjęta jako partner biznesowy.

Po dołączeniu organizacji jako partnera biznesowego użytkownik organizacji, który zainicjował wniosek o zostanie partnerem biznesowym, jest identyfikowany jako użytkownik administratora i otrzymuje uprawnienia do dołączania dodatkowych autoryzowanych użytkowników witryny handlu elektronicznego B2B. Następnie ci autoryzowani użytkownicy mogą składać zamówienia w imieniu partnera biznesowego.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Włącz funkcję handlu elektronicznego B2B w centrali Commerce

Funkcja handlu elektronicznego B2B w centrali Commerce umożliwia organizacjom dołączanie partnerów biznesowych i definiowanie administratorów. Ta funkcja umożliwia również administratorom tworzenie użytkowników i zespołów partnerów biznesowych oraz zarządzanie nimi, a także przypisywanie im określonych ról. Wreszcie, umożliwia użytkownikom partnerów biznesowych tworzenie szablonów zamówień i używanie istniejących zamówień do ponownego zamawiania produktów.

Aby włączyć funkcję handlu elektronicznego B2B w centrali Commerce, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie danymi**.
1. Na karcie **Wszystkie** filtruj pole **Moduł**, używając terminu **Handel detaliczny i inny**.
1. Znajdź i wybierz funkcję o nazwie **Włącz korzystanie z możliwości eCommerce B2B**, a następnie wybierz opcję **Włącz teraz**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Utwórz sekwencję numerów i dodaj ją do wspólnych parametrów Commerce

Sekwencje numerów są używane do generowania czytelnych, unikatowych identyfikatorów dla rekordów danych głównych i rekordów transakcji, które muszą mieć identyfikatory. Aby uzyskać więcej informacji na temat sekwencji numerów, zobacz temat pomocy [Omówienie sekwencji numerów](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview).

Aby utworzyć sekwencję numerów i dodać ją do parametrów współdzielonych aplikacji Commerce w centrali Commerce, wykonaj następujące kroki.

1. Przejdź do **Retail i Commerce \> Ustawienia centrali \> Numery kolejne \> Numery kolejne** i utwórz sekwencję numerów.
1. Przejdź do **Retail i Commerce \> Ustawienia centrali \> Parametry \> Wspólne parametry Commerce** i dodaj nową sekwencję numerów do odwołania do **Identyfikator hierarchii klientów**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Konfigurowanie użytkownika administratora dla nowego partnera biznesowego

Potencjalni partnerzy biznesowi mogą zainicjować proces dołączania do witryny handlu elektronicznego B2B, przesyłając żądanie dołączenia za pośrednictwem łącza w witrynie. Gdy potencjalny użytkownik partnera biznesowego wybierze łącze, może podać szczegóły wymagane do dołączenia i rejestracji. Po przesłaniu żądania zostanie wyświetlona strona potwierdzenia przesłania. Jeśli przesłanie zostanie zatwierdzone, żądający (czyli użytkownik, który zainicjował żądanie dołączenia) staje się administratorem partnera biznesowego.

Aby zatwierdzić i skonfigurować administratora partnera biznesowego w programie Commerce Headquarters, wykonaj następujące kroki.

1. Wybierz **Handel detaliczny i inny Dane IT \> Harmonogram dystrybucji**.
1. Uruchom zadanie **P-0001**, aby ściągnąć wszystkich partnerów biznesowych przy dołączaniu żądań do centrali w programie Commerce Headquarters.
1. Po pomyślnym uruchomieniu zadania **P-0001** przejdź do **Retail i Commerce IT \> Odbiorca** oraz uruchom zadanie **Synchronizuj odbiorców i partnerów biznesowych z trybu asynchronicznego**. Po pomyślnym uruchomieniu tego zadania żądania dołączania są tworzone jako rekordy prospektów w centrali commerce. Pole **Identyfikator typu** w tych rekordach jest ustawione na **prospekt B2B**.
1. Przejdź do strony **Odbiorcy \> Wszyscy potencjalni klienci** i otwórz stronę Prospekty.
1. Wybierz rekord prospektu dla nowego partnera biznesowego, aby otworzyć stronę szczegółów prospektu.
1. Na karcie **Ogólne** wybierz pozycję **Konwertuj \> Zatwierdź/odrzuć**, aby zatwierdzić lub odrzucić wniosek o przyjęcie. Gdy pojawi się komunikat potwierdzenia, potwierdź, że chcesz kontynuować proces, i zatwierdź żądanie. Następnie na adres e-mail wnioskutora zostanie wysłana wiadomość e-mail w celu potwierdzenia, że ich organizacja została zatwierdzona jako partner biznesowy.

    Po zatwierdzeniu wniosku w polu **Stan** rekordu prospektu jest ustawiana wartość **Zatwierdzone**. Ponadto w systemie są tworzone dwa nowe rekordy odbiorcy: rekord odbiorcy organizacji **Typu organizacji** partnera biznesowego oraz rekord odbiorcy **Typ osoby** dla osoby żądacej. Zostanie również utworzony rekord hierarchii odbiorcy dla partnera biznesowego. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Przejdź do **Retail i Commerce IT \> Harmonogram dystrybucji** i uruchom zadanie **1010** (**Odbiorcy**), aby przesunąć nowo utworzone rekordy hierarchii odbiorców i odbiorców do bazy danych kanału.

Po zatwierdzeniu żądania i zsynchronizowaniu rekordów klientów i hierarchii klientów z bazą danych kanału żądający może zalogować się do witryny handlu elektronicznego B2B przy użyciu adresu e-mail podanego podczas przesyłania żądania. Użytkownicy mogą używać przepływu rejestracji w celu zdefiniowania hasła dla swojego konta.

## <a name="onboard-additional-business-partner-users"></a>Dodatkowi użytkownicy partnera biznesowego

Użytkownik administrator partnera biznesowego może w razie potrzeby do witryny sieci web B2B handlu elektronicznego dołączać dodatkowych użytkowników partnerów biznesowych.

Aby do witryny sieci web B2B handlu elektronicznego do pracy dołączać dodatkowych użytkowników partnerów biznesowych, należy wykonać następujące kroki.

1. Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
1. Przejdź do **Moje konto \> Użytkownicy orgznizacji \> Wyświetl szczegóły** i wybierz **Dodaj użytkownika**.
1. Wprowadź wymagane informacje, a następnie wybierz przycisk **Zapisz**. W polu stan nowego użytkownika jest ustawiona wartość **Oczekująca**.

    Po uruchomieniu zadania **P-0001** i **Synchronizuj odbiorców i partnerów biznesowych z trybu asynchronicznego** w programie Commerce Headquarters zostanie utworzony rekord odbiorcy **Typu osoby** dla nowegoużytkownika. Ten rekord odbiorcy jest również skojarzony z rekordem hierarchii odbiorcy odpowiedniego partnera biznesowego. Ponadto na adres e-mail nowego użytkownika wysyłana jest wiadomość e-mail z powiadomieniem, że został on dodany jako użytkownik organizacji partnera biznesowego i może teraz zalogować się do witryny handlu elektronicznego B2B.

1. Uruchom zadanie **1010** (**Odbiorcy**), aby zsynchronizować nowego użytkownika partnera biznesowego z bazą danych kanału sprzedaży.

Po zsynchronizowaniu rekordu odbiorcy stan użytkownika w witrynie B2B handlu elektronicznego jest ustawiany na **Aktywny**, a nowy użytkownik może zalogować się do witryny B2B handlu elektronicznego, używając swojego adresu e-mail. Użytkownicy mogą używać przepływu rejestracji w celu zdefiniowania hasła dla swojego konta.

## <a name="edit-business-partner-user-details"></a>Edytowanie szczegółów użytkownika-partnera biznesowego

Aby edytować szczegóły użytkowników partnerów biznesowych, wykonaj poniższe kroki.

1. Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
1. Przejdź do **Moje konto \> Użytkownicy organizacji \> Wyświetl szczegóły**, wybierz przycisk **Edytuj** (symbol symbolu myszy), dokonaj wymaganych zmian, a następnie wybierz pozycję **Zapisz**. Zmiany zostaną wprowadzone dopiero po uruchomieniu zadań **P-0001**, **Synchronizuj odbiorców i partnerów biznesowych z trybu asynchronicznego** oraz uruchomienia zadań **1010** (**Odbiorcy**).

## <a name="remove-a-business-partner-user"></a>Usuń użytkownika partnera biznesowego

W razie potrzeby administrator może usunąć istniejących użytkowników organizacji partnera biznesowego z listy użytkowników, którzy mają dostęp do witryny sieci web B2B handlu elektronicznego.

Aby usunąć użytkownika partnera biznesowego, wykonaj następujące kroki.

1. Zaloguj się do witryny B2B handlu elektronicznego jako administrator.
1. Przejdź do **Moje konto \> Użytkownicy orgznizacji \> Wyświetl szczegóły** i wybierz przycisk **Usuń** (symbol X). Gdy pojawi się komunikat zatwierdzenia, potwierdź, że chcesz usunąć użytkownika. Zmiany zostaną wprowadzone dopiero po uruchomieniu zadań **P-0001**, **Synchronizuj odbiorców i partnerów biznesowych z trybu asynchronicznego** oraz uruchomienia zadań **1010** (**Odbiorcy**).

> [!NOTE]
> Usunięcie użytkownika z listy użytkowników, którzy mogą uzyskać dostęp do witryny sieci web B2B handlu elektronicznego, spowoduje usunięcie odpowiedniego rekordu odbiorcy z rekordu hierarchii odbiorcy partnera biznesowego. Jednak sam rekord odbiorcy nie został usunięty z Commerce headquarters.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Dołączanie partnera biznesowego i użytkowników w centrali programu Commerce Headquarters

Administratorzy mogą dołączać partnerów biznesowych i użytkowników bezpośrednio w programie Commerce Headquarters.

Aby dołączyć partnerów biznesowych i użytkowników w centrali Commerce, wykonaj następujące kroki.

1. Utwórz rekord odbiorcy **Typ organizacji** dla organizacji partnera biznesowego.
1. Utwórz rekordy odbiorcy **typu Osoba** dla użytkowników partnera biznesowego. Upewnij się, że dla każdego odbiorcy jest określony podstawowy adres e-mail.
1. W przypadku każdego rekordu odbiorcy **typu Osoba**, który musi być wskazany jako użytkownik administratora organizacji partnera biznesowego, na skróconej karcie **Sieci sprzedaży** ustaw opcję **Administrator B2B** na wartość **Tak**.
1. Utwórz identyfikator hierarchii odbiorcy. W polu **Nazwa** wprowadź nazwę.
1. W polu **Organizacja** wpisz partnera biznesowego organizacji klienta.
1. Wybierz **Dodaj**, a następnie wybierz odbiorcę w polu **Nazwa**.
1. Powtórz ten proces, aby dodać dodatkowych odbiorców do hierarchii.

## <a name="additional-information"></a>Informacje dodatkowe

- Wszystkie zadania wymienione w tym temacie można skonfigurować do uruchamiania zgodnie z harmonogramem w formacie wsadowym. Oczekiwania jest takie, że partnerzy biznesowi konfigurują w razie potrzeby zadania wsadowe.
- Obecnie tylko jeden rekord użytkownika / klienta można wyznaczyć jako użytkownika administratora, a tę rolę można zmienić tylko w centrali Commerce. Nie ma wsparcia dla funkcji samoobsługi, które pozwalają partnerom biznesowym na wyznaczanie wielu administratorów lub zmianę administratorów w witrynach handlu elektronicznego B2B.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Chociaż można zdefiniować limity wydatków dla użytkowników, wymuszanie limitów wydatków podczas procesu wprowadzania zamówienia nie zostało jeszcze wdrożone.
- Cała logika biznesowa i sprawdzanie poprawności działania użytkownika w witrynie handlu elektronicznego B2B są oparte na konfiguracji rekordu klienta, który jest mapowany na użytkownika w siedzibie firmy Commerce.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny handlu elektornicznego B2B](set-up-b2b-site.md)

[Tworzenie hierarchii modelowania organizacji dla organizacji B2B](org-model.md)

[Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B](payment-method.md)

[Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego](quantity-limits.md)

[Omówienie sekwencji identyfikatorów](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]