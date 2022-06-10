---
title: Moduł potwierdzenia zamówienia
description: W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e74ffbdfe57f9220cc9ed85edae4270409165b41
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780391"
---
# <a name="order-confirmation-module"></a>Moduł potwierdzenia zamówienia

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły potwierdzenia zamówienia i sposób ich używania w Microsoft Dynamics 365 Commerce.

Moduł potwierdzenia zamówienia służy do wyświetlania szczegółów potwierdzenia zamówienia po jego złożeniu. Zawiera on identyfikator potwierdzenia zamówienia, informacje kontaktowe zamówienia oraz inne szczegóły zamówienia, takie jak zakupione towary, informacje o płatności, opcje odbioru oraz metodę wysyłki.

## <a name="order-confirmation-module-properties"></a>Właściwości modułu potwierdzenia zamówienia

| Nazwa właściwości  | Wartości | Opis |
|----------------|--------|-------------|
| Nagłówek        | Tekst nagłówka i znacznik nagłówka (**H1**, **H2**, **H3**, **H4**, **H5** lub **H6**) | Moduł potwierdzający zamówienie może mieć nagłówek. Domyślnie w nagłówku jest używany znacznik nagłówka **H2**. Jednak znacznik można zmienić, aby spełniał wymagania dotyczące dostępności. |
| Numer osoby kontaktowej | Tekst | Numer kontaktowy może być podawany dla pytań związanych z zamówieniami. |
| Wyświetlanie informacji o przedziałach czasu na potrzeby odbiorów | Prawda lub Fałsz | Ta właściwość jest dostępna w Dynamics 365 Commerce w wersji 10.0.15 i nowszych. Gdy wartość wynosi prawda, wyświetla informacje o przedziale czasu odbioru, jeśli jest podany dla przedmiotu do odbioru|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a>Moduły, których można używać na stronie potwierdzenia zamówienia

Podczas tworzenia strony potwierdzenia zamówienia można dodać także inne odpowiednie moduły oprócz modułu potwierdzenia zamówienia. Oto kilka przykładów:

- **Moduł Rekomendacje** — moduł rekomendacji może zostać dodany do strony potwierdzenia zamówienia w celu zaproponowania odbiorcy innych produktów.
- **Moduły marketingowe** — dowolny moduł marketingowy można dodać do strony potwierdzenia zamówień, aby wyświetlić zawartość marketingową.

## <a name="add-an-order-confirmation-module-to-a-page"></a>Dodawanie modułu potwierdzenia zamówienia do strony

Aby dodać moduł potwierdzenia zamówienia do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon potwierdzenia zamówienia**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd szablonu. Moduł potwierdzenia zamówienia nie będzie renderowany, ponieważ wymaga kontekstu numeru potwierdzenia zamówienia.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Utwórz nowa stronę**, w obszarze **Nazwa strony** wprowadź **Strona potwierdzenia zamówienia**, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz szablon** wybierz **Strona potwierdzenia zamówienia**, który utworzyłeś, a następnie wybierz **Dalej**.
1. W sekcji **Wybierz układ** wybierz układ strony (na przykład **Układ elastyczny**), a następnie wybierz **Dalej**.
1. W sekcji **Przegląd i zakończenie** przejrzyj konfigurację strony. Jeśli chcesz edytować informacje na stronie, wybierz pozycję **Wstecz**. Jeśli informacje na stronie są poprawne, wybierz pozycję **Utwórz stronę**. 
1. W gnieździe **Głównym** w module **Strony domyślnej** wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj moduł**.
1. W oknie dialogowym **Wybierz moduł** wybierz moduł **Potwierdzenie zamówienia** i wybierz przycisk **OK**.
1. W okienku właściwości modułu potwierdzenia zamówienia wybierz pozycję **Nagłówek** obok symbolu ołówka.
1. W polu **Tekst nagłówka** okna dialogowego **Nagłówek** wpisz tekst **Potwierdzenie zamówienia**, a następnie wybierz **OK**.
1. Wybierz **Zapisz**, a następnie wybierz opcję **Podgląd**, aby wyświetlić podgląd strony.
1. Wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Moduł koszyka](add-cart-module.md)

[Moduł ikony koszyka](cart-icon-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł płatności](payment-module.md)

[Moduł adresu wysyłki](ship-address-module.md)

[Moduł opcji dostawy](delivery-options-module.md)

[Moduł informacji o odbiorze](pickup-info-module.md)

[Moduł karty upominkowej](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
