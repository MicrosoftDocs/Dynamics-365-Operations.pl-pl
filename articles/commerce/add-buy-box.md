---
title: Moduł pola zakupu
description: W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
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
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811148"
---
# <a name="buy-box-module"></a>Moduł pola zakupu

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

W tym temacie opisano moduły pola zakupu i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Termin *pole zakupu* zazwyczaj odnosi się do obszaru strony zawierającej szczegóły produktu, która jest „powyżej zakładki”, oraz zawiera wszystkie ważne informacje wymagane do dokonania zakupu produktu. (Obszar „powyżej zakładki” jest widoczny po pierwszym załadowaniu strony, dzięki czemu użytkownicy nie muszą przewinąć w dół, aby ją wyświetlić.)

Moduł pola zakupu to specjalny pojemnik, który służy do przechowywania wszystkich modułów wyświetlanych w polu zakupu na stronie szczegółów produktu.

Adres URL strony szczegóły produktu zawiera identyfikator produktu. Wszystkie informacje wymagane do wyrenderowania modułu pola zakupu pochodzą z tego identyfikatora produktu. Jeśli identyfikator produktu nie zostanie podany, moduł pola zakupu nie będzie poprawnie renderowany na stronie. Z tego względu nie można używać modułu pola zakupu na żadnej stronie, która nie ma kontekstu produktu (np. strony głównej lub strony marketingowej).

## <a name="buy-box-module-properties-and-slots"></a>Qłaściwości modułu pola zakupu i gniazda 

Jako kontener, moduł pola zakupu steruje pewnymi podstawowymi właściwościami, takimi jak szerokość. Ustawienie szerokość określa, czy moduły w kontenerze muszą mieścić się w tym kontenerze, czy też mogą wypełniać ekran.

Na stronie szczegółów produktu pole zakupu jest podzielone na dwa regiony: region multimediów po lewej stronie i region treści po prawej stronie. Te dwa regiony są reprezentowane przez gniazda w module pola zakupu. Każde gniazdo jest wstępnie skonfigurowane w taki sposób, aby akceptowało tylko określone moduły obsługiwane przez gniazdo. Na przykład gniazdo **Multimedia** obsługuje tylko moduł galeria nośników.

Domyślnie współczynnik szerokości kolumn dla regionu multimedialnego i obszaru zawartości to 2:1. Jednak szerokość kolumn może zostać zastąpiona przez motyw. Ponadto na urządzeniach przenośnych obydwa regiony są ułożone w stos, dzięki czemu jeden region jest wyświetlany pod drugim regionem.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Moduły, których można używać w module pola zakupu

- **Galeria multimediów** — ten moduł służy do prezentowania obrazów produktu na stronie szczegółów produktu. Może on obsługiwać jeden lub wiele obrazów. System obsługuje również miniatury obrazów. Miniatury obrazów mogą być ułożone poziomo (jako wiersz pod obrazem) lub w pionie (jako kolumna obok obrazu). Moduł Galeria multimediów można dodać do gniazda **Multimedia** w module pole zakupu. Obecnie obsługuje tylko obrazy i wideo.
- **Tytuł produktu** — ten moduł pokazuje tytuł produktu na stronie szczegóły produktu. Domyślnie jest używany znacznik nagłówka **H1**, ale znacznik nagłówka może zostać zmieniony zgodnie z potrzebą
- **Ocena produktu** — ten moduł pokazuje klasyfikacje gwiazdkowe na podstawie klasyfikacji odbiorców dla produktu. Moduł pole zakupu pobiera oceny produktów dla każdego produktu z usługi ocen.
- **Cena produktu** — ten moduł pokazuje cenę produktu. Cena obejmuje ceny i rabaty przekreślenia.
- **Opis produktu** — ten moduł pokazuje opis produktu.
- **Konfiguracja produktu** — ten moduł pokazuje rozmiar, styl i wymiary produktu. Selektory wymiarów mogą być ułożone pionowo lub mogą być wyświetlane obok siebie. Po wybraniu wariantu produktu inne właściwości w polu zakupu (np. opis produktu i obrazy) są aktualizowane w celu odzwierciedlenia informacji o wariantach.
- **Ilość produktu** — ten moduł jest używany do konfigurowania ilości produktu. Ustawienie ogranicza ilość produktu lub wariantu, który można dodać do koszyka.
- **Dodaj do koszyka** — ten moduł służy do wykonywania akcji „Dodaj do koszyka”. Do koszyka można dodać tylko produkt lub wariant. Oznacza to, że produktu głównego nie można dodać do koszyka. Moduł ma właściwość **Przejdź do koszyka**, która może zostać ustawiona przez autora witryny. Jeśli ta właściwość ma wartość **prawda**, użytkownik jest zabierany do strony koszyka za każdym razem, gdy jest wyzwalane działanie „dodaj do koszyka”. Jeśli ustawiono wartość **fałsz**, klient może kontynuować przeglądanie na stronie Szczegóły produktu po dodaniu towarów do koszyka.
- **Dodaj do listy życzeń** — ten moduł służy do dodawania towaru do listy życzeń klienta. Tylko produkt lub wariant można dodać do listy życzeń. Ponadto klient musi być zalogowany do witryny. Moduł zawiera logikę obsługi błędów w celu upewnienia się, że oba te warunki są spełnione.
- **Znajdź w sklepie** — ten moduł wyzwala przepływ „kupowanie online, odbiór w sklepie”.
- **Odbierz w sklepie** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Domyślnie w tym module są wyświetlane sklepy, które znajdują się w promieniu 50-milowej lokalizacji odbiorcy. Promień wyszukiwania można jednak dostosować w module. W przypadku każdego sklepu sprawdzanie magazynowe jest wykonywane, jeśli funkcja sprawdzania magazynu jest włączona, a jest wyświetlana odpowiednia wiadomość w magazynie lub brak w magazynie.
- **Wyszukiwanie sklepu według Bing Maps** – Tego modułu można używać wewnątrz modułu odbioru w sklepie. Klienci firmy umożliwiają wyszukiwanie sklepów, wprowadzając lokalizację. Interfejs programowania aplikacji (API) Bing Maps służy do konwertowania określonej lokalizacji na szerokość geograficzną i długość geograficzną. Jeśli ten moduł jest używany, wyświetlane są tylko sklepy znajdujące się w pobliżu bieżącej lokalizacji klienta, a klient nie może wyszukać innej lokalizacji.
- **Blok zawartości sformatowanej** — ten moduł może wskazywać wiadomość, którą autor lub sprzedawca chce promować w polu zakupu, np. „w przypadku problemów z zamówieniem, kontakt 1-800-FABRIKAM” lub „bezpłatna wysyłka przy zamówieniach za ponad $100” Komunikaty są prowadzone przez system zarządzania zawartością (CMS).

## <a name="buy-box-module-settings"></a>Ustawienia modułu pola zakupu

Moduły pól zakupu mają trzy ustawienia, które można skonfigurować:

- **Ilość maksymalna** — Maksymalna liczba każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach. Ta kontrola zapasów jest realizowana zarówno dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie. Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.
- **Bufor zapasów** — zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów. Można więc zdefiniować bufor dla zapasów. Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów. W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów, dzięki czemu inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.

## <a name="retail-server-interaction"></a>Interakcja z serwerem Retail

Moduł pola zakupu pobiera informacje o produktach za pomocą interfejsów API serwera Retail. Identyfikator produktu ze strony Szczegóły produktu służy do pobierania wszystkich informacji.

## <a name="add-a-buy-box-module-to-a-page"></a>Dodawanie modułu pola zakupu do strony

Aby dodać moduł pola zakupu do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz fragment o nazwie **fragment pola zakupu** i dodaj do niego moduł pola zakupu.
1. Do gniazda **Multimedia** w module pole zakupu dodaj moduł galerii multimediów.
1. W gnieździe **Zawartości** modułu pole zakupu dodaj następujące moduły: tytuł produktu, klasyfikacja produktu, cena produktu, opis produktu, konfiguracja produktu, fodaj do koszyka, fodaj do listy życzeń i znajdź w sklepie. Istnieje możliwość ponownego rozmieszczenia modułów w gnieździe **Zawartości** w celu uzyskania żądanego układu.
1. Wybierz moduł Znajdź w sklepie. W gnieździe wewnątrz tego modułu dodaj moduł odbioru w sklepie.
1. W gnieździe wewnątrz modułu odbioru w sklepie dodaj wyszukiwanie w sklepie według modułu Bing Maps.
1. Zaewidencjonuj stronę i opublikuj ją.
1. Utwórz szablon strony Szczegóły produktu i nadaj mu nazwę **Szablon PDP**.
1. Dodaj stronę domyślną.
1. W **Głównym** gnieździe na stronie domyślnej dodaj fragment pola zakupu.
1. Zapisz szablon, zaewidencjonuj go i opublikuj.
1. Za pomocą utworzonego właśnie szablonu utwórz stronę o nazwie **strona PDP**.
1. W **Głównym** gnieździe na nowej stronie dodaj fragment pola zakupu.
1. Zapisz i zobacz podgląd strony. Do adresu URL podglądu strony należy dodać parametr dotyczący ciągu kwerendy **?productid=&lt;product id&gt;**. W ten sposób kontekst produktu jest używany do ładowania i renderowania strony podglądu.
1. Zaewidencjonuj stronę i opublikuj ją. Na stronie Szczegóły produktu powinno pojawić się pole zakupu.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł koszyka](add-cart-module.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
