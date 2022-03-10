---
title: Włączanie wyszukiwania zamówień dla realizacji transakcji gościa
description: W tym temacie opisano sposób włączania wyszukiwania zamówień dla realizacji transakcji gościa w aplikacji Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: a2a10b122faae354b0ea002e43a9bd60157f6216
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891507"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Włączanie wyszukiwania zamówień dla realizacji transakcji gościa

[!include [banner](includes/banner.md)]

W tym temacie opisano sposób włączania wyszukiwania zamówień dla realizacji transakcji gościa w aplikacji Microsoft Dynamics 365 Commerce.

Funkcja wyszukiwania dla realizacji transakcji gościa umożliwia klientom, którzy dokonają zakupów jako użytkownicy goście, wyszukiwanie ich zamówień. Funkcja wyszukiwania zamówień jest przydatna, gdy klienci chcą wykonać takie akcje, jak sprawdzenie stanu realizacji produktów w zamówieniu, sprawdzenie adresu, na który wysłano zamówienie, ponowne zamówienie produktu lub potwierdzenie sklepu, z którego zostanie odebrane zamówienie.

Klienci, którzy składali zamówienia jako zarejestrowani użytkownicy, mogą zobaczyć szczegóły swoich zamówień po zalogowaniu się, ale klienci korzystający z funkcji realizacji zamówienia gość w celu składania zamówień nie mogą. Jeśli jednak funkcja wyszukiwania zamówień dla realizacji transakcji gościa jest włączona, jest dostępny formularz, za pomocą którego klienci mogą wyszukiwać zamówienia złożone przez nich jako gości. W tym formularzu klienci mogą wprowadzić identyfikator potwierdzenia zamówienia oraz (opcjonalnie) adres e-mail podany podczas realizacji zamówienia.

Ponadto link lub przycisk, który powoduje, że klient bezpośrednio znajduje się na stronie szczegółów zamówienia, może być dołączony do dowolnych wiadomości e-mail dotyczących transakcji. Ten link lub przycisk będzie działać dla zamówień, które są składane zarówno przez zarejestrowanych użytkowników, jak i przez użytkowników gości.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Włączanie niezbędnych funkcji w centrali rozwiązania Commerce

Aby włączyć funkcję wyszukiwania zamówień w przypadku realizacji transakcji gościa, należy włączyć następujące funkcje w obszarze **Obszary robocze \> Zarządzanie funkcjami** w centrali rozwiązania Commerce.

| Funkcja | Cel |
|---------|---------|
| Funkcja włączenia wyszukiwania szczegółów zamówienia przez anonimowych użytkowników rozwiązania Retail | Ta funkcja udostępnia interfejs użytkownika w parametrach rozwiązania Commerce, który umożliwia włączanie interfejsu API wyszukiwania zamówień dla nieuwierzytelnionych użytkowników i konfigurowanie sposobu wyświetlania danych osobowych. |
| Włącz generowanie mocniejszego identyfikatora odwołania do kanału | Ta funkcja generuje bezpieczniejszy 12-znakowy identyfikator odwołania kanału (identyfikator potwierdzenia zamówienia), który może zostać przekazany w ciągu zapytania podczas wyszukiwania zamówienia. |
| Generuj spójny format identyfikatora odwołania kanału między kanałami | Ta funkcja generuje identyfikator odwołania do bezpiecznego kanału dla zamówień, które są składane za pośrednictwem witryny e-commerce, punktu sprzedaży w sklepie detalicznym (POS) lub centrum obsługi. Aby można było włączyć tę funkcję, należy włączyć funkcję **Włącz generowanie silniejszego identyfikatora odwołania kanału**. |

Po włączeniu funkcji **wyrażania zgody na wyszukiwanie szczegółów zamówienia anonimowego użytkownika handlu detalicznego** należy włączyć interfejs API obsługujący wyszukiwanie nieuwierzytelnianych zamówień w centrali rozwiązania Commerce. Kliknij kolejno opcje **Retail i Commerce \> Ustawienia centrali \> Parametry \> Zamówienia klienta**. Na stronie **Zamówienia klienta** na skróconej karcie **Wyszukiwanie zamówień** ustaw opcję **Włącz wyszukiwanie zamówień nieuwierzytelnionych** na wartość **Tak**, tak jak pokazano na poniższej ilustracji.

## <a name="manage-the-display-of-personal-data"></a>Zarządzanie wyświetlaniem danych osobowych

Skrócona karta **Wyszukiwanie zamówień** na stronie **Zamówienia klienta** w centrali rozwiązania Commerce zawiera pole **Uwzględnij dane osobowe w wyszukiwaniu zamówień gościa**, które umożliwia kontrolowanie, czy dane osobowe są pokazywane klientom. Te dane osobowe obejmują adres wysyłkowy klienta oraz ostatnie cztery cyfry numeru karty kredytowej klienta. Domyślnie dane osobowe nie widoczne dla klientów, jeśli włączono wyszukiwanie zamówień nieuwierzytelnionych. W poniższej tabeli przedstawiono dostępne opcje.

| Opcja | Wynik |
|--------|--------|
| Nigdy | Wartość domyślna. Żadne dane osobowe nie są wyświetlane w wyszukiwaniach zamówień. Zarejestrowani użytkownicy, którzy są zalogowani, wyszukują zamówienia utworzone przez nich po zalogowaniu, dzięki którym będą mogli zobaczyć swoje dane osobowe. |
| Tylko zamówienia gości | Dane osobowe są wyświetlane w wyszukiwaniach zamówień utworzonych przez gości. Jeśli zamówienie zostało utworzone przez zarejestrowanego użytkownika, musi się on zalogować, aby zobaczyć swoje dane osobowe. |
| Wszystkie zamówienia | Dane osobowe nie są wyświetlane w żadnych wyszukiwaniach zamówień. |

> [!NOTE]
> Te opcje określają, kiedy dane osobowe, takie jak adres klienta i ostatnie cztery cyfry numeru jego karty kredytowej, są pokazywane anonimowym użytkownikom gościom. Aby chronić prywatność zarejestrowanych klientów, zaleca się wybór opcji **Tylko zamówienia gości**. Jednak najbezpieczniejszą opcją jest **Nigdy**.

Po zmianie wartości pola **Uwzględnij dane osobowe w wyszukiwaniu zamówień gości** należy uruchomić zadanie 1070 (**Konfiguracja kanału**) w centrali rozwiązania Commerce, przechodząc do pozycji **Retail i Commerce \> Retail i Commerce — składniki IT \> Harmonogram dystrybucji**.

## <a name="configure-the-order-lookup-module"></a>Konfigurowanie modułu wyszukiwania zamówień

Moduł wyszukiwania zamówień w bibliotece modułów Commerce służy do renderowania formularza używanego przez użytkowników gości do wyszukiwania zamówień. Moduł wyszukiwania zamówień może zostać uwzględniony w gnieździe treści dowolnej strony, która nie wymaga zalogowania się klienta. Aby uzyskać informacje dotyczące sposobu konfigurowania modułu, zobacz [Moduł wyszukiwania zamówień](order-lookup-module.md).

## <a name="configure-the-order-details-page"></a>Konfigurowanie strony szczegółów zamówienia

Aby użytkownicy gości zobaczyli szczegóły swojego zamówienia, strona szczegółów zamówienia w witrynie e-commerce musi być skonfigurowana tak, aby nie wymagała logowania. Aby wyłączyć wymaganie logowania dla strony szczegółów zamówienia, otwórz stronę konstruktora witryn Commerce, zaznacz w widoku drzewa gniazdo **Strona domyślna (wymagane)** i wyczyść pole wyboru **Wymaga zalogowania się?** u dołu okienka właściwości po prawej stronie.

## <a name="add-a-link-to-order-details-in-transactional-emails"></a>Dodawanie linku do szczegółów zamówienia w wiadomościach e-mail dotyczących transakcji

W wiadomościach e-mail związanych z zamówieniem można podać link lub przycisk, który powoduje, że odbiorcy są przekierowywani do strony szczegółów zamówienia. Aby dodać ten link lub przycisk, utwórz hiperlink HTML, które wskazuje stronę szczegółów zamówienia w witrynie e-commerce, a następnie przekaż identyfikator potwierdzenia zamówienia i adres e-mail odbiorcy jako parametry adresu URL, tak jak pokazano w poniższym przykładzie.

`<a href="https://[domain]/[orderdetailspage]?confirmationId=%orderconfirmationid%&propertyName=email&propertyValue=%customeremailaddress%" target="_blank">View my order status</a>`

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł wyszukiwania zamówień](order-lookup-module.md)

[Konfigurowanie profilu powiadomienia](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
