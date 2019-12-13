---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696768"
---
# <a name="cart-module"></a>Moduł koszyka

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł koszyka to pojemnik, który służy do przechowywania wszystkich modułów wymaganych do zaprezentowania przedmiotów znajdujących się w koszyku. Dotyczy to na przykład wszystkich towarów, które zostały dodane do koszyka, podsumowania zamówień i kodów promocyjnych.

Moduł koszyka renderuje dane na podstawie identyfikatora koszyka. Identyfikator koszyka to plik cookie przeglądarki dostępny w witrynie.

## <a name="cart-module-properties-and-slots"></a>Właściwości modułu koszyka i gniazda

Jako kontener, moduł koszyka steruje pewnymi podstawowymi właściwościami, takimi jak nagłówek i szerokość. Nagłówek to zazwyczaj tekst, na przykład **Torba na zakupy**, **Twój koszyk** lub **Elementy w koszyku**. Ustawienie szerokość określa, czy moduły w kontenerze muszą mieścić się w tym kontenerze, czy też mogą wypełniać ekran.

Strona koszyka jest podzielona na wiele regionów: pozycje w wierszu koszyka, podsumowanie zamówień i realizacja transakcji oraz funkcja „Znajdź w sklepie”. Każdy region jest mapowany na gniazdo w module koszyka, a każde gniazdo akceptuje wstępnie zdefiniowany zbiór modułów.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduły, których można używać w module koszyka

- **Pozycje w wierszu koszyka** — w tym module jest wyświetlane podsumowanie wszystkich towarów, które zostały dodane do koszyka. Informacje te obejmują tytuł produktu, wybrane wymiary, cenę, ilość i rabaty. Moduł ten obsługuje również akcje, takie jak „Usuń z koszyka” i „Dodaj do listy życzeń”. Dla każdego towaru w wierszu dostępna jest opcja wysyłki towaru lub odebrania go ze sklepu. Tę opcję należy skonfigurować osobno w module odbioru w sklepie.
- **Podsumowanie zamówienia** — w tym module jest wyświetlane podsumowanie zamówień. Informacje te obejmują sumę częściową, koszty wysyłki, podatki i oszczędności. Dla tego modułu można skonfigurować nagłówek.
- **Kod promocji** — ten moduł pozwala odbiorcy na wykupu kodów promocyjnych. Kod promocyjny może zostać zastosowany lub usunięty.
- **Realizacja transakcji** — ten moduł inicjuje akcję realizacji transakcji i przekierowuje użytkownika do strony realizacja transakcji. Dla tego modułu należy skonfigurować trzy łącza:

    - **Realizacja transakcji** — to łącze zmusza odbiorców do logowania, jeśli nie zostały jeszcze zalogowane.
    - **Realizacja transakcji Gościa** — to łącze pozwala anonimowym odbiorcom złożyć zamówienia. Jest wyświetlana tylko wtedy, gdy odbiorcy nie są zalogowani.
    - **Powrót do zakupów** — klienci tego łącza powinni przejść na stronę główną lub na dowolną inną stronę, aby móc kontynuować zakupy.

- **Blok zawartości sformatowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka. Komunikaty są prowadzone przez system zarządzania zawartością (CMS). Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.
- **Odbierz w sklepie** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Domyślnie w tym module są wyświetlane sklepy, które znajdują się w promieniu 50-milowej lokalizacji odbiorcy. Promień wyszukiwania można jednak dostosować w module. W przypadku każdego sklepu sprawdzanie magazynowe jest wykonywane, jeśli funkcja sprawdzania magazynu jest włączona, a jest wyświetlana odpowiednia wiadomość w magazynie lub brak w magazynie.
- **Wyszukiwanie sklepu według Bing Maps** – Tego modułu można używać wewnątrz modułu odbioru w sklepie. Klienci firmy umożliwiają wyszukiwanie sklepów, wprowadzając lokalizację. Interfejs programowania aplikacji do geokodowania Bing Maps (API) służy do konwersji lokalizacji podanej przez klienta na szerokość i długość geograficzną. Jeśli ten moduł nie jest używany, wyświetlane są tylko sklepy znajdujące się w pobliżu bieżącej lokalizacji klienta, a klient nie może wyszukać innej lokalizacji.

## <a name="cart-module-settings"></a>Ustawienia modułu koszyka

Moduły koszyka mają trzy ustawienia, które można skonfigurować:

- **Ilość maksymalna** — Maksymalna liczba każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach. Ta kontrola zapasów jest realizowana zarówno dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie. Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.
- **Bufor zapasów** — zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów. Można więc zdefiniować bufor dla zapasów. Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów. W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów, dzięki czemu inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.

## <a name="retail-server-interaction"></a>Interakcja z serwerem Retail

Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API serwera Retail. Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z serwera Retail.

## <a name="add-a-cart-module-to-a-page"></a>Dodawanie modułu koszyka do strony

Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz fragment o nazwie **fragment koszyka** i dodaj do niego moduł koszyka.
1. W gnieździe **pozycje wiersza koszyka** dodaj moduł towarów w wierszu koszyka.
1. W gnieździe **Podsumowanie zamówienia** dodaj moduł podsumowania zamówienia.
1. W gnieździe **Kod promocyjny** dodaj moduł kodu promocyjnego.
1. W gnieździe **Realizacji transakcji** dodaj moduł realizacji transakcji.
1. W gnieździe **Znajdź w sklepie** dodaj pobranie w module sklep.
1. W module Odbiór w sklepie wybierz miejsce **Wyszukiwanie w sklepie** i dodaj wyszukiwanie w sklepie według modułu Bing Maps.
1. Zaewidencjonuj fragment i opublikuj go.
1. Utwórz szablon o nazwie **szablon koszyka** i dodaj do niego właśnie utworzony fragment koszyka.
1. Zapisz szablon, zaewidencjonuj go i opublikuj.
1. Utwórz stronę, która korzysta z nowego szablonu.
1. Zapisz i zobacz podgląd strony.
1. Zaewidencjonuj stronę i opublikuj ją.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
