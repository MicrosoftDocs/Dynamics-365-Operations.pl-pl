---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025443"
---
# <a name="cart-module"></a>Moduł koszyka


[!include [banner](includes/banner.md)]

W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł koszyka służy do wyświetlania towarów, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji. Dotyczy to na przykład wszystkich towarów, które zostały dodane do koszyka i podsumowania zamówień. Umożliwia także stosowanie lub usuwanie kodów promocyjnych przez odbiorcę.

Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości. Ponadto obsługuje łącze **Powrót do zakupów**. Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.

Moduł koszyka renderuje dane na podstawie identyfikatora koszyka. Identyfikator koszyka to plik cookie przeglądarki dostępny w witrynie.

## <a name="cart-module-properties-and-slots"></a>Właściwości modułu koszyka i gniazda

Moduł koszyka ma właściwość **Nagłówka**, która może być ustawiona na wartości takie jak **Torba na zakupy** i **Elementy w koszyku**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduły, których można używać w module koszyka

- **Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka. Komunikaty są prowadzone przez system zarządzania zawartością (CMS). Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.
- **Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy. Moduł wyboru sklepu jest zintegrowany z aplikacją do geokodowania Bing Maps Geocoding (API) służy do konwersji lokalizacji na szerokość i długość geograficzną. Klucz interfejsu API map usługi Bing jest wymagany i należy go dodać do strony udostępnione parametry sieci sprzedaży w Dynamics 365 Retail. Ten moduł obsługuje dwie właściwości, **Promień wyszukiwania** i **Łącze Warunki świadczenia usługi**. Właściwość **Promień wyszukiwania** definiuje promień wyszukiwania dla sklepów w milach. Jeśli nie określono żadnej wartości, używany jest domyślny promień wyszukiwania, 50 mil. Jeśli używana jest mapa usług Bing lub usługa zewnętrzna, **Łącze Warunki świadczenia usługi** może być używana do udostępniania łącza do warunków świadczenia usługi. Dla usługi Bing Maps jest wymagane łącze Warunki świadczenia usługi. 

## <a name="cart-module-settings"></a>Ustawienia modułu koszyka

Moduły koszyka mają następujące ustawienia, które można skonfigurować w **Ustawienia witryny \> Rozszerzenia**:

- **Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach. Ta kontrola zapasów jest realizowana zarówno dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie. Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.
- **Bufor zapasów** — ta właściwość służy do określania numeru buforowego zapasów. Zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów. Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów. W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów i inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.
- **Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**. Tę trasę można skonfigurować na poziomie witryny. Odbiorcy tej konfiguracji przebiorą odbiorcę z powrotem na stronę główną lub na inną stronę w witrynie.

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit. Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Dodawanie modułu koszyka do strony

Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz fragment o nazwie **Fragment koszyka** i dodaj do niego moduł koszyka.
1. Dodaj nagłówek do modułu koszyka.
1. Dodaj moduł Wybór sklepu do modułu koszyka.
1. Zapisz fragment, zakończ jego edycję, a następnie go opublikuj.
1. Utwórz szablon o nazwie **Szablon koszyka** i dodaj do niego właśnie utworzony fragment koszyka.
1. Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.
1. Utwórz stronę, która korzysta z nowego szablonu.
1. Zapisz i zobacz podgląd strony.
1. Zakończ edytowanie strony i opublikuj go.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
