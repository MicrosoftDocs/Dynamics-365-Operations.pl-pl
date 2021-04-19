---
title: Moduł pola zakupu
description: W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: dce3c8adcd2926e60d001bddb5c278fac6860268
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796229"
---
# <a name="buy-box-module"></a>Moduł pola zakupu

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

Termin *pole zakupu* zazwyczaj odnosi się do obszaru strony zawierającej szczegóły produktu, która jest „powyżej zakładki”, oraz zawiera wszystkie ważne informacje wymagane do dokonania zakupu produktu. (Obszar „powyżej zakładki” jest widoczny po pierwszym załadowaniu strony, dzięki czemu użytkownicy nie muszą przewinąć w dół, aby ją wyświetlić.)

Moduł pola zakupu to specjalny pojemnik, który służy do przechowywania wszystkich modułów wyświetlanych w polu zakupu na stronie szczegółów produktu.

Adres URL strony szczegóły produktu zawiera identyfikator produktu. Wszystkie informacje wymagane do wyrenderowania modułu pola zakupu pochodzą z tego identyfikatora produktu. Jeśli identyfikator produktu nie zostanie podany, moduł pola zakupu nie będzie poprawnie renderowany na stronie. Z tego względu moduł pola zakupu może być używany tylko na stronach z kontekstem produktu. Aby można było z niego skorzystać na stronie, która nie ma kontekstu produktu (np. strony głównej lub strony marketingowej), należy wykonać dodatkowe dostosowania.

Poniższy obraz pokazuje przykład modułu kupującego na stronie ze szczegółowymi informacjami o produkcie.

![Przykład modułu pola zakupu](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Qłaściwości modułu pola zakupu i gniazda 

Na stronie szczegółów produktu pole zakupu jest podzielone na dwa regiony: region multimediów po lewej stronie i region treści po prawej stronie. Domyślnie stosunek szerokości kolumny region multimedialny do szerokości kolumny obszaru zawartości wynosi 2:1. Na urządzeniach przenośnych obydwa regiony są ułożone w stos, dzięki czemu jeden region jest wyświetlany pod drugim regionem. Motywów można używać do dostosowywania szerokości kolumn i rangi układania.

Moduł pudełka z kupowaniem umożliwia renderowanie tytułu, opisu, ceny i klasyfikacji produktu. Klienci mogą również wybrać warianty produktu, które mają różne atrybuty produktu, takie jak rozmiar, styl i kolor. Po wybraniu wariantu produktu inne właściwości w polu zakupu (np. opis produktu i obrazy) są aktualizowane w celu odzwierciedlenia informacji o wariantach. 

Dostępny jest selektor ilości, dzięki czemu odbiorcy mogą określić ilość towarów do zakupienia. Maksymalną ilość, jaką można zakupić, można zdefiniować w ustawieniach oddziału.

W polu kupowania klienci mogą również wykonywać takie działania, jak dodawanie produktu do koszyka, dodawanie produktu do ich listy życzeń oraz wybieranie lokalizacji odbioru. Te akcje można wykonać dla produktu lub wariantu produktu. Aby dodać produkt do listy życzeń, odbiorca musi się zalogować.

Motywów można używać do usuwania lub zmieniania kolejności właściwości produktu pola zakupu oraz formantów akcji. 

## <a name="module-properties"></a>Właściwości modułu

- **Znacznik nagłówka** — ta właściwość definiuje znacznik nagłówka dla produktu. Jeśli pole zakupu znajduje się u góry strony, właściwość ta powinna mieć ustawioną wartość **h1**, aby odpowiadała standardom dostępności. 

- **Włącz zalecenia typu „Kup podobne”** — ta właściwość umożliwia wyświetlenie w polu zakupu łączy do produktów wyglądających podobnie do aktualnie wyświetlanego towaru. Ta funkcja jest dostępna w Commerce w wersji 10.0.13 i nowszej.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduły, których można używać w module pola zakupu

- **Galeria multimediów** — ten moduł służy do prezentowania obrazów produktu na stronie szczegółów produktu. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Modułu galerii multimediów](media-gallery-module.md).
- **Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy. Aby uzyskać więcej informacji dotyczących tego modułu, przejdź do [Modułu selektor sklepów](store-selector.md).
- **Udostępnij na portalach społecznościowych** — ten moduł można dodać do pola zakupu, aby umożliwić użytkownikom udostępnianie informacji o produktach w mediach społecznościowych. Aby uzyskać więcej informacji, zajrzyj do [Moduł udostępniania w mediach społecznościowych](social-share-module.md).

## <a name="buy-box-module-settings"></a>Ustawienia modułu pola zakupu

Następujące ustawienia modułu pola zakupu mogą być skonfigurowane w **Ustawienia witryny \> Rozszerzenia**:

- **Limit ilości dla wiersza koszyka** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Zapasy** — Aby uzyskać informacje dotyczące sposobu stosowania ustawień zapasów, należy zapoznać się z tematem [stosowanie ustawień zapasów](inventory-settings.md).
- **Dodaj produkt do koszyka** — Ta właściwość służy do określania zachowania po dodaniu towaru do koszyka. Możliwe wartości są **Przejdź do koszyka**, **Nie przechodź do koszyka** i **Wyświetl powiadomienia**. Gdy wartość jest ustawiona na **Przejdź do strony koszyka**, użytkownicy są wysyłani na stronę koszyka po dodaniu towaru. Gdy wartość jest ustawiona na **Nie przechodź do strony koszyka**, użytkownicy nie są wysyłani na stronę koszyka po dodaniu towaru. Gdy wartość jest ustawiona na **Wyświetl powiadomienie**, użytkownicy będą wyświetlali powiadomienie o potwierdzeniu i mogą kontynuować przeglądanie na stronie szczegóły produktu. 

> [!IMPORTANT]
> Ustawienia w witrynie **Dodaj produkt do koszyka** są dostępne w wydaniu Dynamics 365 Commerce 10.0.11. W przypadku aktualizacji ze starszej wersji Dynamics 365 Commerce należy ręcznie zaktualizować plik appsettings.json. Aby uzyskać instrukcje dotyczące aktualizowania pliku appsettings.json, zajrzyj do [Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

Poniższy rysunek przedstawia przykład powiadomienia o potwierdzeniu „dodanego do koszyka” w witrynie Fabrikam.

![Przykład modułu powiadomienia](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Moduł kupna pobiera informacje o produkcie za pomocą interfejsów programistycznych (API) aplikacji Commerce Scale Unit. Identyfikator produktu ze strony Szczegóły produktu służy do pobierania wszystkich informacji.

## <a name="add-a-buy-box-module-to-a-page"></a>Dodawanie modułu pola zakupu do strony

Aby dodać moduł pola zakupu do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Przejdź do **Fragmenty**, a następnie wybierz opcję **Nowy**, aby stworzyć nowy fragment.
1. W oknie dialogowym **Nowy fragment** wybierz moduł **Pole zakupu**.
1. W obszarze **Nazwa fragmentu** wprowadź nazwę **Fragment pola zakupu**, a następnie kliknij przycisk **OK**.
1. W gnieździe **Galeria multimediów**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Galeria multimediów** i wybierz przycisk **OK**.
1. W gnieździe **Selektor sklepu**, w którym znajduje się moduł pola zakupu wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodawanie modułu** wybierz moduł **Selektor sklepu** i wybierz przycisk **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować fragment, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Szablonu**, a następnie wybierz **Nowy**, aby utworzyć nowy szablon.
1. W oknie dialogowym **Nowy szablon**, w obszarze **Nazwa szablonu** wprowadź **Szablon PDP**, a następnie wybierz **OK**.
1. W gnieździe **Treść** wybierz wielokropek (**...**), a następnie wybierz **Dodaj moduł**.
1. W oknie dialogowym **Dodaj moduł** wybierz moduł **Strona domyślna** i wybierz przycisk **OK**.
1. Na domyślnej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Wybieranie fragmentu** wybierz utworzony wcześniej fragment **Fragment pola zakupu**, a następnie kliknij **OK**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować szablon, a następnie wybierz opcję **Publikuj**, aby ją opublikować.
1. Przejdź do **Strony**, a następnie wybierz opcję **Nowy**, aby utworzyć nową stronę.
1. W oknie dialogowym **Wybierz szablon** wybierz szablon **Szablon PDP**. W sekcji **Nazwa strony** przejdź do **Strona PDP**, a następnie wybierz przycisk **OK**.
1. Na nowej stronie wybierz gniazdo **Główne**, następnie wybierz przycisk wielokropka (**...**), a następnie wybierz pozycję **Dodaj fragment**.
1. W oknie dialogowym **Wybieranie fragmentu** wybierz utworzony wcześniej fragment **Fragment pola zakupu**, a następnie kliknij **OK**.
1. Zapisz i zobacz podgląd strony. Do adresu URL podglądu strony należy dodać parametr dotyczący ciągu kwerendy **?productid=&lt;product id&gt;**. W ten sposób kontekst produktu jest używany do ładowania i renderowania strony podglądu.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować. Na stronie Szczegóły produktu powinno pojawić się pole zakupu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie biblioteki modułów](starter-kit-overview.md)

[Moduł wyboru sklepu](store-selector.md)

[Moduł galerii multimediów](media-gallery-module.md)

[Moduł kontenera](add-container-module.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)

[Moduł udostępniania społeczności](social-share-module.md)

[Obliczanie dostępności zapasów dla kanałów sprzedaży detalicznej](calculated-inventory-retail-channels.md)

[Aktualizacje zestawu SDK i biblioteki modułów](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]