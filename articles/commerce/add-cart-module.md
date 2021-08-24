---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f2db61cf23c217365274297c6e9878a4eb5679f8d9502cb70484372ae43f6b18
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716891"
---
# <a name="cart-module"></a>Moduł koszyka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Moduł koszyka wyświetla towary, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji. Ten moduł pokazuje również podsumowanie zamówień i pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.

Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości. Ponadto obsługuje łącze **Powrót do zakupów**. Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.

Moduł koszyka służy do renderowania danych na podstawie identyfikatora koszyka, który jest plikiem cookie przeglądarki dostępnym w witrynie. 

Poniższy obraz przedstawia przykład strony koszyka w witrynie Fabrikam.

![Przykład modułu koszyka w witrynie Fabrikam.](./media/cart2.PNG)

Poniższy obraz przedstawia przykład strony koszyka w witrynie Fabrikam. W tym przykładzie istnieje opłata manipulacyjna dla pozycji w wierszu.

![Przykład modułu koszyka z opłatą manipulacyjną dla pozycji w wierszu.](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>Właściwości modułu koszyka i gniazda

| Właściwość | Wartości | opis |
|----------------|--------|-------------|
| Nagłówek | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Nagłówek koszyka, na przykład „Torba na zakupy” lub „Produkty w Twoim koszyku”. |
| Pokaż błędy niedostępnych w magazynie | **Prawda** lub **Fałsz** | Jeśli ta właściwość ma wartość **Prawda**, na stronie kozyka będą widoczne błędy dotyczące zapasów. Zaleca się ustawienie tej właściwości na **Prawda**, jeśli sprawdzanie zapasów jest wykonywane w odniesieniu do danego oddziału. |
| Pokaż opłaty transportowe dla pozycji w wierszu | **Prawda** lub **Fałsz** | Jeśli ta właściwość ma wartość **Prawda**, pozycje w wierszu koszyka będą pokazywały opłaty transportowe, jeśli te informacje są dostępne. Ta funkcja nie jest obsługiwana w motywie Fabrikam, ponieważ użytkownicy wybierają tylko wysyłkę w ramach przepływu realizacji transakcji. Tę funkcję można jednak włączyć w innych przepływach pracy, jeśli ma ona zastosowania. |
| Wyświetl dostępne promocje| **Prawda** lub **Fałsz** | Jeśli właściwość ma wartość **Prawda**, w koszyku są pokazuje dostępne promocje oparte na pozycjach w koszyku. Ta funkcja nie jest dostępna tylko w Dynamics 365 Commerce w wersji 10.0.16. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduły, których można używać w module koszyka

- **Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka. Komunikaty są prowadzone przez system zarządzania zawartością (CMS). Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.
- **Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy. Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł selector sklepów](store-selector.md).

## <a name="module-properties"></a>Właściwości modułu

Następujące ustawienia modułu koszyka mogą być skonfigurowane w **Ustawienia witryny \> Rozszerzenia**:

- **Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Zapasy** — Aby uzyskać informacje dotyczące sposobu stosowania ustawień zapasów, należy zapoznać się z tematem [stosowanie ustawień zapasów](inventory-settings.md).
- **Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**. Marszrutę można skonfigurować na poziomie witryny, umożliwiając detalistom przejęcie odbiorcy z powrotem na stronę główną lub na inną stronę w witrynie.

> [!IMPORTANT]
> W Dynamics 365 Commerce w wersji 10.0.14 i nowszych towary w koszyku są agregowane na podstawie ustawień zdefiniowanych w profilu funkcji online sklepu internetowego w module Commerce Headquarter. Aby uzyskać więcej informacji na temat tworzenia profilu funkcji online i ustawiania właściwości wymaganych do agregacji, należy zapoznać się z tematem [Tworzenie profilu funkcji online](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit. Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Dodawanie modułu koszyka do strony

Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Koszyk**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę **Fragment koszyka**, a następnie kliknij przycisk **OK**.
1. Wybierz gniazdo **Koszyk**.
1. W okienku właściwości po prawej stronie wybierz symbol ołówka, wprowadź tekst nagłówka w polu, a następnie zaznacz symbol znacznika wyboru.
1. W gnieździe **Koszyk** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Selektor sklepu** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wpisz nazwę szablonu.
1. W drzewie konspektu wybierz **Treść**, następnie wybierz wielokropek (**...**), a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Wybierz fragment** wybierz **Fragment koszyka**, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz utworzony szablon, wprowadź nazwę strony, a następnie kliknij przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł szczegółów zamówienia](order-confirmation-module.md)

[Moduł karty upominkowej](add-giftcard.md)

[Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md)

[Tworzenie profilu funkcji online](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]