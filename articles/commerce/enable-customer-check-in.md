---
title: Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży
description: W tym artykule opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: ae53657c95128eae793f670bd9dbc31d9fac0fe4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885152"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Włączanie powiadomień zameldowania odbiorcy w punkcie sprzedaży

[!include [banner](includes/banner.md)]

W tym artykule opisano sposób włączania powiadomień zameldowania odbiorcy w punkcie sprzedaży systemu Microsoft Dynamics 365 Commerce.

W wiadomościach e-mail „zamówienie gotowe do odbioru” organizacje mogą zamieścić łącze lub przycisk, aby klienci powiadomili sklep, że znajdują się w budynku i oczekują na przyniesienie paczki. Odbiorcy otrzymają następnie potwierdzenie zameldowania, a sklep otrzyma powiadomienie jako zadanie w aplikacji punktu sprzedaży. To zadanie służy jako monit o skojarzenie sprzedaży w celu dostarczenia zamówienia do pojazdu odbiorcy. Wtedy odbiorca nie musi wchodzić do sklepu.

Przepływ pracy zameldowania odbiorcy można również skonfigurować w taki sposób, aby gromadził od odbiorców dodatkowe informacje, takie jak numer miejsca parkingowego, marka, model i kolor jego pojazdu oraz instrukcje dostawy. Informacje te mogą ułatwić sprzedawcy realizację zamówienia.

## <a name="enable-customer-check-in"></a>Włączanie zameldowania odbiorcy

Po włączeniu funkcji zameldowania odbiorcy Commerce generuje identyfikator potwierdzenia zamówienia (nazywany także identyfikatorem odwołania do kanału). Ponadto generuje identyfikatory potwierdzenia zamówienia dla zamówień, które są tworzone za pośrednictwem punktu sprzedaży (POS) lub kanałów w centrum obsługi. 

Aby włączyć funkcję zameldowania odbiorcy w centrali Commerce, wykonaj następujące kroki.

1. Kliknij kolejno opcje **Obszary robocze \> Zarządzanie funkcjami**.
2. Wyszukaj funkcję **Generowanie jednolitego formatu identyfikatora odwołania do kanału w różnych kanałach**. 
3. Wybierz funkcję, a następnie w okienku właściwości naciśnij przycisk **Włącz teraz**. 

## <a name="create-a-check-in-confirmation-page"></a>Tworzenie strony potwierdzenia zameldowania

W witrynie handlu elektronicznego trzeba utworzyć nową stronę, która będzie stanowiła środowisko potwierdzenia zameldowania. Po dodatkowej konfiguracji strona może również zawierać formularz, który zbiera dodatkowe informacje od odbiorców, które ułatwią realizację zamówienia. Aby uzyskać informacje dotyczące sposobu skonfigurowania strony i modułu, zobacz [Moduł zameldowania odbiorcy](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Konfigurowanie szablonu transakcyjnej wiadomości e-mail

Musisz dodać łącze lub przycisk **Jestem tutaj** do szablonu transakcyjnej wiadomości e-mail, którą odbiorcy otrzymują, gdy ich zamówienie jest gotowe do odbioru. Odbiorcy będą używać tego łącza lub przycisku w celu powiadomienia sklepu, że przybyli, aby odebrać zamówienie. 

Dodaj łącze lub przycisk do szablonu, który jest mapowany na typ powiadomienia **Zakończenie pakowania** i tryb dostawy używany do realizacji zamówienia „przy krawężniku”. W szablonie utwórz przycisk lub link HTML, który wskazuje adres URL utworzonej strony potwierdzenia zameldowania i zawiera nazwy oraz wartości parametrów, tak jak pokazano w poniższym przykładzie.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Aby uzyskać więcej informacji dotyczących konfigurowania szablonów wiadomości e-mail, zobacz temat [Dostosowywanie transakcyjnych wiadomości e-mail zależnie od trybu dostawy](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>W punkcie sprzedaży zostanie utworzone zadanie potwierdzenia zameldowania

Gdy klient powiadomi sklep, że jest gotowy do odebrania zakupu, na stronie zameldowania jest wyświetlany komunikat potwierdzenia oraz opcjonalny kod PIN z identyfikatorem potwierdzenia zamówienia klienta. Jednocześnie na liście zadań w punkcie sprzedaży dla sklepu, w którym klient odbiera zamówienie, jest tworzone zadanie. Zadanie to zawiera wszystkie informacje o odbiorcy i zamówieniu wymagane do realizacji zamówienia. Pole instrukcji w zadaniu zawiera wszystkie informacje zebrane od odbiorcy za pośrednictwem formularza informacji dodatkowych.

## <a name="end-to-end-testing"></a>Kompleksowe testowanie

Zameldowanie klienta wymaga przekazania określonych parametrów i wartości do strony zameldowania, a następnie do interfejsu API zameldowania klienta. Dlatego najprostszym rozwiązaniem jest przetestowanie tej funkcji w środowisku, w którym można utworzyć i zapakować zamówienie testowe. W ten sposób można wygenerować wiadomość e-mail z informacją „zamówienie gotowe do pobrania” oraz adresem URL zawierającym wymagane nazwy i wartości parametrów.

Aby przetestować funkcję zameldowania klienta, wykonaj następujące kroki.

1. Utwórz stronę zameldowania klienta, a następnie dodaj i skonfiguruj moduł zameldowania odbiorcy. Aby uzyskać więcej informacji, zobacz temat [Moduł zameldowania do odbioru](check-in-pickup-module.md). 
1. Zaewidencjonuj stronę, ale jej nie publikuj.
1. Dodaj poniższy link do szablonu wiadomości e-mail wywoływanego przez typ powiadomienia o zakończeniu pakowania dla metody dostawy „odbiór”. Aby uzyskać więcej informacji, zobacz temat [Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych](email-templates-transactions.md).

    - **W środowiskach przedprodukcyjnych (UAT):** dodaj fragment kodu z sekcji [Konfigurowanie szablonu transakcyjnej wiadomości e-mail](#configure-the-transactional-email-template) znajdującej się wcześniej w tym artykule.
    - **W środowiskach produkcyjnych:** dodaj następujący kod z komentarzem, aby nie wpływał on na istniejących klientów.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Utwórz zamówienie, w którym określono metodę dostawy „odbiór”.
1. Po otrzymaniu wiadomości e-mail, która jest wyzwalana przez typ powiadomienia o zakończeniu pakowania, przetestuj przepływ zameldowania, otwierając stronę zameldowania, która zawiera adres URL dodany wcześniej. Ponieważ adres URL zawiera flagę `&preview=inprogress`, przed wyświetleniem strony zostanie wyświetlony monit o uwierzytelnienie.
1. Wprowadź dodatkowe informacje wymagane do skonfigurowania modułu.
1. Sprawdź, czy widok potwierdzenia zameldowania jest pokazywany poprawnie.
1. Otwórz termin w punkcie sprzedaży w sklepie, w którym zamówienie zostanie odebrane.
1. Wybierz kafelek **Zamówienia do odbioru** i sprawdź, czy jest wyświetlane zamówienie.
1. Sprawdź, czy dodatkowe informacje skonfigurowane w module zameldowania są wyświetlane w okienku szczegółów.

Po sprawdzeniu, czy funkcja zameldowania obsługi klienta działa kompleksowo, wykonaj następujące kroki.

1. Opublikuj stronę zameldowania.
1. Jeśli testujesz w środowisku produkcyjnym, usuń komentarz dotyczący adresu URL w szablonie wiadomości e-mail „zamówienie gotowe do odbioru”, aby było widoczne link lub przycisk **Jestem tutaj**. Następnie ponownie przekaż szablon.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł zameldowania do odbioru](check-in-pickup-module.md)

[Dostosowywanie wiadomości e-mail dotyczących transakcji według metod dostawy](customize-email-delivery-mode.md)

[Tworzenie szablonów wiadomości e-mail na potrzeby zdarzeń transakcyjnych](email-templates-transactions.md)
