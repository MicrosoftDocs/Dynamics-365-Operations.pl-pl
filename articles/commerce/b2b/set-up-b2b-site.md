---
title: Konfigurowanie witryny handlu elektornicznego B2B
description: W tym temacie opisano sposób skonfigurowania witryny handlu elektronicznego (B2B) w Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/23/2021
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
ms.openlocfilehash: 461e79f63569bbfe77f9075c562a5b1f3da28cc2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018862"
---
# <a name="set-up-a-b2b-e-commerce-site"></a>Konfigurowanie witryny wykorzystywanej na potrzeby handlu elektronicznego B2B

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

Witryny handlu elektronicznego typu business-to-business (B2B) zapewniają kilka kluczowych funkcji, które optymalizują przepływ pracy dla użytkownika B2B. W tym temacie opisano sposób skonfigurowania witryny handlu elektronicznego B2B w Microsoft Dynamics 365 Commerce. Przechodzi przez moduły i ustawienia witryny, które należy skonfigurować, aby umożliwić scenariusze specyficzne dla B2B.

## <a name="prerequisites"></a>Wymagania wstępne

- Aby skonfigurować witrynę B2B handlu elektronicznego, należy włączyć i skonfigurować określone funkcje w centrali Commerce, zgodnie z opisem w tym temacie.
- Podstawowe funkcje, takie jak odkrywanie produktów, strony szczegółów produktów, koszyk i realizacja transakcji, są obsługiwane przez te same moduły, które są używane w witrynach handlu elektronicznego między przedsiębiorstwami a konsumentami (B2C). Autorzy witryn powinni znać wszystkie moduły obsługiwane przez Dynamics 365 Commerce. Aby uzyskać więcej informacji, zobacz [Przegląd biblioteki modułów](../starter-kit-overview.md).
- W tym temacie założono, że autorzy witryn rozumieją podstawy narzędzia do tworzenia witryn Commerce, szablonów, fragmentów i stron, dzięki czemu mogą włączyć funkcje B2B w witrynach handlu elektronicznego.

## <a name="site-level-settings"></a>Ustawienia na poziomie witryny

Dostęp do ustawień na poziomie witryny można uzyskać w Konstruktorze witryn w **Ustawienia witryny \> Rozszerzenia**. Następujące dwa ustawienia na poziomie witryny dotyczą scenariuszy B2B:

- **Włącz płatności na konta odbiorcy** — ta właściwość umożliwia użytkownikom płacenie za zamówienia przy użyciu kont odbiorcy. Dostępne wartości są **Włączone dla klientów B2B**, **Włączone dla klientów B2C**, **Włączone dla wszystkich klientów** i **Wyłączone dla wszystkich klientów**. Jeśli witryna B2B obsługuje konta odbiorców, należy wybrać opcję **Włączone dla klientów B2C**.
- **Włącz limity ilości zamówienia** — ta właściwość umożliwia ustawienie limitów liczby towarów, które można zamówić dla każdego produktu lub kategorii. Dostępne wartości są **Włączone dla klientów B2B**, **Włączone dla klientów B2C**, **Włączone dla wszystkich klientów** i **Wyłączone dla wszystkich klientów**.

> [!NOTE]
> Podczas uaktualniania do najnowszej wersji biblioteki modułów należy wykonać dodatkowe kroki, aby upewnić się, że opisane wcześniej ustawienia lokacji są dostępne w Twoim środowisku. Aby uzyskać więcej informacji, zobacz [Zaktualizuj plik app.settings.json](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="create-business-partner-sign-up-pages"></a>Tworzenie stron rejestracji partnera biznesowego

Aby zostać partnerem biznesowym, użytkownicy muszą najpierw przesłać prośbę o partnera biznesowego. Łącze do strony z prośbą o partnera biznesowego będzie dostępne na stronie głównej B2B, dzięki czemu użytkownicy będą mogli zainicjować proces. Gdy użytkownicy prześlą żądanie partnera biznesowego, otrzymają potwierdzenie, że wniosek został złożony. 

### <a name="create-a-business-partner-request-page"></a>Tworzenie strony wniosku nowego partnera biznesowego

Moduł **Rejestracji partnera** na stronie z prośbą o partnera biznesowego służy do inicjowania wniosków użytkowników o zostanie partnerami biznesowymi. Ten moduł umożliwia zbieranie informacji o użytkownikach wymaganych do procesu rejestracji. Ponadto do przechwytywania adresu użytkownika jest używany moduł **Adres konta biznesowego**.

Aby skonfigurować stronę żądania partnera biznesowego w Konstruktorze witryn, wykonaj następujące kroki.

1. Utwórz szablon o nazwie **Rejestracja**. Szablon powinien zawierać następujące moduły:

    - Rejestracja partnera
    - Łącze do stron nadrzędnych
    - Nagłówek
    - Stopka
    - Blok zawartości
    - Blok tekstu
    - Kolekcja produktów

1. Użyj szablonu **Rejestracja**, aby utworzyć stronę o nazwie **Wniosek partnera biznesowego**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj łącze do strony głównej, a jako tekst łącza wprowadź **Strona główna**.
1. W gnieździe **Kontener** dodaj moduł **Rejestracja partnera** poniżej modułu **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź pozycję **Zostać partnerem biznesowym**.
1. W gnieździe **Rejestracji partnera** dodaj moduł **Adres konta biznesowego**.
1. W gnieździe **Kontener** dodaj moduł **Blok tekstu** poniżej modułu **Rejestracja partnera**. W tym miejscu można zdefiniować warunki dotyczące procesu rejestracji.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.

### <a name="create-a-business-partner-request-confirmation-page"></a>Utwórz stronę potwierdzenia prośby o partnera biznesowego

Po przesłaniu prośby o partnera biznesowego, strona z potwierdzeniem powinna zostać wyświetlona użytkownikowi, aby potwierdzić przesłanie. 

Aby skonfigurować i skonfigurować stronę potwierdzenia żądania w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj wcześniej stworzonego szablonu **Rejestracja**, aby utworzyć stronę o nazwie **Potwierdzenie wnioseku partnera biznesowego**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W module **Kontenera** dodaj moduł **Bloku zawartości**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Przesłane żądanie**. W polu **Tekst sformatowany** wprowadź, że **Żądanie zostało przesłane**. W obszarze **Łącza** skonfiguruj łącze do strony głównej, a jako tekst łącza wprowadź **Powrót do zakupów**.
1. Dodaj inny moduł **Kontenera** i dodaj do niego moduł **Kolekcji produktów**.
1. Skonfiguruj moduł **Kolekcja produktów** z listą propozycji lub kategorii, która ma zostać wyświetlona na stronie.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.

Aby dodać łącze do strony potwierdzenia żądania w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Przejdź do strony **Żądanie partnera biznesowego**, która została wcześniej utworzona, i wybierz pozycję **Edytuj**. 
1. Wybierz gniazdo modułu **Rejestracji partnera**. W okienku właściwości, w obszarze **Łącze do strony Potwierdzenie rejestracji**, skonfiguruj łącze do utworzonej wcześniej strony żądania partnera biznesowego. 
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="add-a-business-partner-request-link-to-the-home-page"></a>Dodawanie łącza żądania partnera biznesowego do strony głównej

Po utworzeniu stron z prośbą o rejestrację i potwierdzeniem partnera biznesowego należy udostępnić stronę rejestracji za pośrednictwem łącza na stronie głównej. To zadanie można wykonać, dodając łącze do dowolnego modułu **Bloku zawartości** na stronie głównej.

Aby dodać łącze prośby o partnera biznesowego do strony głównej w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Przejdź do strony głównej witryny i wybierz **Edytuj**.
1. Wybierz gniazdo modułu **Blok zawartości**. W okienku właściwości modułu, w obszarze **Łącza**, skonfiguruj łącze do strony żądania partnera biznesowego utworzonego wcześniej, a następnie wprowadź pozycję **Zarejestruj, aby być partnerem biznesowym** lub podobnym tekstem łącza. Dodaj obraz, zgodnie z potrzebą.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="account-management-landing-page"></a>Strona docelowa zarządzania kontami

Strona docelowa zarządzania kontem zawiera wszystkie informacje dotyczące zarządzania kontem, które są wymagane w przypadku witryn handlu elektronicznego B2B i B2C. Tę stronę mogą wyświetlać tylko zalogowani użytkownicy.

Aby utworzyć i skonfigurować stronę docelową zarządzania kontem B2B w Konstruktorze witryn, wykonaj następujące kroki.

1. Utwórz szablon o nazwie **Zarządzanie kontem**. Szablon powinien zawierać następujące moduły:

    - Nagłówek
    - Stopka
    - Łącze do stron nadrzędnych
    - Kafelek powitalny konta
    - Kafelek ogólny konta
    - Kafelek adresu konta
    - Kafelek listy życzeń konta
    - Kafelek adresu konta
    - Kafelek programu lojalnościowego konta
    - Kafelek Saldo odbiorcy konta
    - Kafelek szablonów zamówień dla konta
    - Użytkownicy organizacji
    - Lista organizacji biznesowych
    - Saldo konta odbiorcy
    - Wiersze szablonu zamówienia
    - Lista szablonu zamówienia
    - Kafelek faktury konta
    - Lista faktur
    - Szczegóły faktury

1. Użyj szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Moje konto**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. 
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj łącze do strony głównej, a jako tekst łącza wprowadź **Strona główna**.
1. W module **Kontenera** dodaj moduł **Kafelek powitalny**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Zapraszamy**.
1. W gnieździe **Głównym** dodaj kolejny moduł **Kontenera** (**Kontener 2**). W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. Ustaw wartość **Wyświetlaj podrzędne** na wartość **Dwa**. 
1. W gnieździe **Kontener 2** dodaj moduł **Ogólny kafelek konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Mój profil**. W obszarze **Łącza** skonfiguruj łącze do strony **Mój profil**. 
1. W gnieździe **Kontener 2** dodaj kolejny moduł **Ogólny kafelek konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Historia zamówienia**. W obszarze **Łącza** skonfiguruj link do strony historii zamówień.
1. W gnieździe **Głównym** dodaj kolejny moduł **Kontenera** (**Kontener 3**). W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. Ustaw wartość **Wyświetlaj podrzędne** na wartość **Dwa**. 
1. W gnieździe **Kontener 3** dodaj moduł **Kafelek adresu konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Mój adres**. W obszarze **Łącza** skonfiguruj łącze do strony **Mój adres**. 
1. W gnieździe **Kontener 3** dodaj moduł **Kafelek listy życzeń konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Moja lista życzeń**. W obszarze **Łącza** skonfiguruj łącze do strony **Moja lista życzeń**.
1. W gnieździe **Głównym** dodaj kolejny moduł **Kontenera** (**Kontener 4**). W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. Ustaw wartość **Wyświetlaj podrzędne** na wartość **Dwa**. 
1. W gnieździe **Kontener 4** dodaj moduł **Użytkownicy organizacji**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Użytkownicy organizacji**. 
1. W gnieździe **Kontener 4** dodaj moduł **Kafelek Saldo odbiorcy konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Kredyt konta**. 
1. W gnieździe **Głównym** dodaj kolejny moduł **Kontenera** (**Kontener 5**). W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. Ustaw wartość **Wyświetlaj podrzędne** na wartość **Dwa**. 
1. W module **Kontener 5** dodaj moduł **Kafelek szablonu zamówienia konta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Szablony zamówienia**. 
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

> [!NOTE] 
> Niektóre sekcje dodane w krokach od 13 do 18 nie pojawią się na kanwie „to, co widzisz, otrzymujesz” (WYSIWIG) w narzędziu do tworzenia witryn, ponieważ wymagają zalogowanego konta B2B.

## <a name="create-and-configure-customer-balance-pages-and-modules"></a>Tworzenie i konfigurowanie stron i modułów salda odbiorcy 

Konta odbiorcy mogą być używane do płacenia za zamówienia. Dostępne saldo na koncie klienta można wyświetlić na stronie zarządzania kontem użytkownika.

### <a name="create-a-customer-balance-page"></a>Utwórz stronę salda klienta 

Zanim zalogowani użytkownicy B2B będą mogli zobaczyć saldo swoich klientów, musisz utworzyć stronę salda klientów. 

Aby utworzyć stronę salda klienta w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Saldo odbiorcy**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj kolejny moduł **Kontenera** (**Kontener 3**). W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**. Ustaw wartość **Wyświetlaj podrzędne** na wartość **Dwa**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**.
1. W gnieździe **Kontener** dodaj moduł **Saldo konta klienta**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Saldo konta**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.
1. Przejdź do strony docelowej zarządzania kontem (**Moje konto**), utworzonej wcześniej.
1. W okienku właściwości modułu **Saldo odbiorcy konta** dodaj łącze do strony salda odbiorcy. 
1. Zapisz i opublikuj podgląd strony.

Została utworzona strona salda klienta, a użytkownicy mogą uzyskać do niej dostęp z poziomu strony docelowej zarządzania kontem.

### <a name="configure-a-checkout-page-so-that-the-customer-balance-can-be-used-as-a-form-of-payment"></a>Skonfiguruj stronę kasy, aby saldo klienta mogło być używane jako forma płatności

Moduł **Płatność na konto odbiorcy** jest wymagany, aby saldo odbiorcy było używane jako formularz płatności. Ten moduł należy dodać do strony realizacji zamówienia jako formy płatności. Aby uzyskać informacje o tym, jak skonfigurować stronę kasy i moduły wymagane do realizacji transakcji, w tym wszystkie szczegóły płatności, zobacz [moduł Realizacja zamówienia](../add-checkout-module.md).

Po skonfigurowaniu strony realizacji zamówienia trzeba dodać moduł **Płatność z konta odbiorcy** do sekcji płatności, a następnie zapisać i opublikować stronę. Użytkownicy B2B będą wtedy mogli zalogować się do witryny handlu elektronicznego i zastosować dostępne saldo klientów do zamówień podczas realizacji transakcji.

Ponadto w przypadku **Konstruktor witryn \> Rozszerzenia** należy upewnić się, że właściwość **Włącz płatności konta odbiorcys** ma wartość **Włącz dla odbiorców B2B**.

## <a name="create-order-template-pages"></a>Tworzenie stron szablonów zamówień

Dla witryny handlu elektronicznego B2B można skonfigurować dwie strony szablonów zamówień: stronę z listą szablonów zamówień i stronę z wierszami szablonu zamówienia.

Strona z listą szablonów zamówień zawiera listę wszystkich dostępnych szablonów zamówień. Jest on ustawiany za pomocą modułu **Lista szablonów zamówień**. Strona z listą szablonów zamówień umożliwia tworzenie lub usuwanie szablonu i dodawanie pozycji w szablonie do koszyka.

Strona wierszy szablonu zamówienia zawiera szczegóły szablonu zamówienia wybranego na stronie z listą szablonów zamówień. Jest on ustawiany za pomocą modułu **Wiersze szablonów zamówień**. Gdy użytkownik wybierze nazwę szablonu na stronie z listą szablonów zamówień, zostanie wyświetlona strona wierszy szablonu zamówienia zawierająca szczegóły szablonu. Użytkownik może następnie wyświetlać i edytować towary w szablonie.

### <a name="create-an-order-templates-list-page"></a>Tworzenie strony listy szablonów zamówień

Aby utworzyć stronę z listą szablonów zamówień w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Szablony zamówień**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**.
1. W gnieździe **Kontener** dodaj moduł **Lista szablonów zamówień**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.
1. Przejdź do strony docelowej zarządzania kontem (**Moje konto**), utworzonej wcześniej.
1. W okienku właściwości modułu **Kafelki szablonów zamówień kont** w obszarze **Łącza** skonfiguruj łącze do utworzonej właśnie strony listy szablonów zamówień.
1. Zapisz i opublikuj podgląd strony.

Utworzono stronę z listą szablonów zamówień, a użytkownicy mogą uzyskać do niej dostęp z poziomu strony docelowej zarządzania kontem.

### <a name="create-an-order-template-lines-page"></a>Utwórz stronę z wierszami szablonu zamówienia

Aby utworzyć stronę z wierszami szablonów zamówień w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Wiersze szablonów zamówień**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**.
1. W gnieździe **Kontener** dodaj moduł **Wiersze szablonów zamówień**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.

## <a name="onboard-business-partner-users"></a>Użytkownicy partnerów biznesowych w trakcie wdrażania

Strona użytkowników organizacji umożliwia administratorowi organizacji partnera biznesowego dołączanie dodatkowych użytkowników z tej organizacji do witryny handlu elektronicznego B2B. Jest on ustawiany za pomocą modułu **Lista organizacji biznesowych**. Na stronie użytkowników organizacji administrator może dodawać i usuwać użytkowników, definiować salda kont i żądać wyciągów dla użytkownika.

Aby utworzyć stronę użytkowników organizacji w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Użytkownicy organizacji**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**.
1. W gnieździe **Kontener** dodaj moduł **Lista organizacji biznesowych**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Użytkownicy organizacji**.
1. W okienku właściwości modułu **Lista organizacji biznesowych** włącz właściwości **Sortowanie tabeli** i **Paginacja tabel**. Ustaw liczbę paginacji na **5**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.
1. Przejdź do strony docelowej zarządzania kontem (**Moje konto**), utworzonej wcześniej.
1. W okienku właściwości modułu **Kafelek użytkowników organizacji** w obszarze **Łącza** skonfiguruj łącze do utworzonej właśnie strony użytkowników organizacji. 
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="create-invoice-pages"></a>Tworzenie stron faktury

Na stronie listy faktur jest wyświetlona lista wszystkich dostępnych faktur. Jest on ustawiany za pomocą modułu **InvoicesList**. Na stronie listy faktur użytkownicy mogą spłacać lub wysyłać prośby o faktury. 

Strona szczegółów faktury zawiera szczegóły faktury wybranej na stronie z listą faktur. Jest on ustawiany za pomocą modułu **Dane do faktury**. Gdy użytkownik wybierze identyfikator faktury na stronie listy faktur, zostanie wyświetlona strona szczegółów faktury zawierająca szczegóły faktury.

### <a name="create-an-invoices-list-page"></a>Tworzenie strony listy faktur

Aby utworzyć stronę z fakturami w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Lista faktur**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**.
1. W module **Kontenera** dodaj moduł **InvoicesList**. W okienku właściwości modułu, w obszarze **Nagłówek** wprowadź **Faktury**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.
1. Przejdź do strony docelowej zarządzania kontem (**Moje konto**), utworzonej wcześniej.
1. W okienku właściwości modułu **Kafelek faktur konta** w obszarze **Łącza** skonfiguruj łącze do utworzonej właśnie strony listy faktur. 
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

### <a name="create-an-invoice-details-page"></a>Tworzenie strony szczegółów faktury

Aby utworzyć stronę szczegółów faktury w narzędziu do tworzenia witryn, wykonaj następujące kroki.

1. Użyj utworzonego wcześniej szablonu **Zarządzania kontem**, aby utworzyć stronę o nazwie **Szczegóły faktur**.
1. W gnieździe **Nagłówek** dodaj fragment nagłówka wstępnie skonfigurowany z nagłówkiem witryny.
1. W gnieździe **Stopka** dodaj fragment stopki wstępnie skonfigurowany ze stopką witryny.
1. W gnieździe **Głównym** dodaj moduł **Kontener**. W okienku właściwości modułu określ wartość **Szerokości** jako **Wypełnij kontener**.
1. W miejscu **Kontener** dodaj moduł **Szlaki nawigacyjne**. W okienku właściwości modułu, w obszarze **Łącza** skonfiguruj link do strony docelowej zarządzania kontem, a jako tekst łącza wprowadź **Moje konto**. Następnie skonfiguruj łącze do strony z listą faktur i wprowadź **Listy faktur** jako tekst łącza.
1. W module **Kontenera** dodaj moduł **Szczegóły faktur**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Opublikuj adres URL strony.

## <a name="add-a-quick-add-module-to-the-cart-page"></a>Dodawanie modułu szybkiego dodawania do strony koszyka

Moduł szybkiego dodawania umożliwia szybkie dodawanie wielu towarów do koszyka przy użyciu identyfikatorów towarów (zwanych także identyfikatorami jednostki magazynowej \[SKU\]). Moduł szybkiego dodawania jest dodawany do strony koszyka witryny.

Aby dodać moduł szybkiego dodawania do strony koszyka w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do strony **Szablony** i wybierz szablon strony koszyka witryny.
1. Wybierz opcję **Edycja**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Szybkie dodawanie** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do lokalizacji **Strony** i wybierz szablon strony koszyka witryny.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Kontener** i wybierz przycisk **OK**.
1. W okienku właściwości modułu **Kontener**, w obszarze **Szerokość** wybierz opcję **Wypełnij kontener**.
1. W gnieździe **Kontener** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Szybkie dodawanie** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

> [!NOTE] 
> Moduł szybkiego dodawania jest dostępny od wersji Commerce 10.0.17. W przypadku aktualizacji ze starszej wersji Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Dodatkowe zasoby

[Przegląd biblioteki modułów](../starter-kit-overview.md)

[Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file)

[Omówienie strony tworzenia](../authoring-home-overview.md)

[Omówienie szablonów i układów](../templates-layouts-overview.md)

[Praca z fragmentami](../work-with-fragments.md)

[Dodawanie nowej strony witryny](../add-new-page.md)

[Moduł realizacji transakcji](../add-checkout-module.md)

[Moduł bloku zawartości](../add-hero-module.md)

[Moduł kolekcji produktów](../product-collection-module-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
