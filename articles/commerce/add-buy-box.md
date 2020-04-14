---
title: Moduł pola zakupu
description: W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3417156cbf3cb20a5190e5e51b61b3423816895a
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154070"
---
# <a name="buy-box-module"></a>Moduł pola zakupu


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Termin *pole zakupu* zazwyczaj odnosi się do obszaru strony zawierającej szczegóły produktu, która jest „powyżej zakładki”, oraz zawiera wszystkie ważne informacje wymagane do dokonania zakupu produktu. (Obszar „powyżej zakładki” jest widoczny po pierwszym załadowaniu strony, dzięki czemu użytkownicy nie muszą przewinąć w dół, aby ją wyświetlić.)

Moduł pola zakupu to specjalny pojemnik, który służy do przechowywania wszystkich modułów wyświetlanych w polu zakupu na stronie szczegółów produktu.

Adres URL strony szczegóły produktu zawiera identyfikator produktu. Wszystkie informacje wymagane do wyrenderowania modułu pola zakupu pochodzą z tego identyfikatora produktu. Jeśli identyfikator produktu nie zostanie podany, moduł pola zakupu nie będzie poprawnie renderowany na stronie. Z tego względu moduł pola zakupu może być używany tylko na stronach z kontekstem produktu. Aby można było z niego skorzystać na stronie, która nie ma kontekstu produktu (np. strony głównej lub strony marketingowej), należy wykonać dodatkowe dostosowania.

## <a name="buy-box-module-properties-and-slots"></a>Qłaściwości modułu pola zakupu i gniazda 

Na stronie szczegółów produktu pole zakupu jest podzielone na dwa regiony: region multimediów po lewej stronie i region treści po prawej stronie. Domyślnie stosunek szerokości kolumny region multimedialny do szerokości kolumny obszaru zawartości wynosi 2:1. Na urządzeniach przenośnych obydwa regiony są ułożone w stos, dzięki czemu jeden region jest wyświetlany pod drugim regionem. Motywów można używać do dostosowywania szerokości kolumn i rangi układania.

Moduł pudełka z kupowaniem umożliwia renderowanie tytułu, opisu, ceny i klasyfikacji produktu. Klienci mogą również wybrać warianty produktu, które mają różne atrybuty produktu, takie jak rozmiar, styl i kolor. Po wybraniu wariantu produktu inne właściwości w polu zakupu (np. opis produktu i obrazy) są aktualizowane w celu odzwierciedlenia informacji o wariantach. 

Dostępny jest selektor ilości, dzięki czemu odbiorcy mogą określić ilość towarów do zakupienia. Maksymalną ilość, jaką można zakupić, można zdefiniować w ustawieniach oddziału.
 
W polu kupowania klienci mogą również wykonywać takie działania, jak dodawanie produktu do koszyka, dodawanie produktu do ich listy życzeń oraz wybieranie lokalizacji odbioru. Te akcje można wykonać dla produktu lub wariantu produktu. Aby dodać produkt do listy życzeń, odbiorca musi się zalogować.

Motywów można używać do usuwania lub zmieniania kolejności właściwości produktu pola zakupu oraz formantów akcji. 

## <a name="module-properties"></a>Właściwości modułu

- **Znacznik nagłówka** — ta właściwość definiuje znacznik nagłówka dla produktu. Jeśli pole zakupu znajduje się u góry strony, właściwość ta powinna mieć ustawioną wartość **h1**, aby odpowiadała standardom dostępności. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduły, których można używać w module pola zakupu

- **Galeria multimediów** — ten moduł służy do prezentowania obrazów produktu na stronie szczegółów produktu. Może on obsługiwać jeden lub wiele obrazów. System obsługuje również miniatury obrazów. Miniatury obrazów mogą być ułożone poziomo (jako wiersz pod obrazem) lub w pionie (jako kolumna obok obrazu). Moduł Galeria multimediów można dodać do gniazda **Multimedia** w module pole zakupu. Obecnie obsługuje tylko obrazy. 
- **Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy. Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł Selector sklepów](store-selector.md).

## <a name="buy-box-module-settings"></a>Ustawienia modułu pola zakupu

Moduły kupowania mają trzy następujące ustawienia, które można skonfigurować w **Ustawienia witryny \> Rozszerzenia**:

- **Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach. Ta kontrola zapasów jest realizowana zarówno dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie. Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.
- **Bufor zapasów** — ta właściwość służy do określania numeru buforowego zapasów. Zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów. Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów. W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów i inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Moduł kupowania pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit. Identyfikator produktu ze strony Szczegóły produktu służy do pobierania wszystkich informacji.

## <a name="add-a-buy-box-module-to-a-page"></a>Dodawanie modułu pola zakupu do strony

Aby dodać moduł pola zakupu do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz fragment o nazwie **fragment pola zakupu** i dodaj do niego moduł pola zakupu.
1. Do gniazda **Multimedia** w module pole zakupu dodaj moduł galerii multimediów.
1. W gnieździe **Wyboru sklepu** w module kupowania dodaj moduł wyboru sklepu.
1. Zaewidencjonuj stronę i opublikuj ją.
1. Utwórz szablon strony Szczegóły produktu i nadaj mu nazwę **Szablon PDP**.
1. Dodaj stronę domyślną.
1. W **Głównym** gnieździe na stronie domyślnej dodaj fragment pola zakupu.
1. Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.
1. Za pomocą utworzonego właśnie szablonu utwórz stronę o nazwie **strona PDP**.
1. W **Głównym** gnieździe na nowej stronie dodaj fragment pola zakupu.
1. Zapisz i zobacz podgląd strony. Do adresu URL podglądu strony należy dodać parametr dotyczący ciągu kwerendy **?productid=&lt;product id&gt;**. W ten sposób kontekst produktu jest używany do ładowania i renderowania strony podglądu.
1. Zapisz stronę, zakończ jej edycję, a następnie ją opublikuj. Na stronie Szczegóły produktu powinno pojawić się pole zakupu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł wyboru sklepu](store-selector.md)

[Moduł kontenera](add-container-module.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
