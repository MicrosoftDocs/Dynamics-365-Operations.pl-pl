---
title: Moduł koszyka
description: W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.openlocfilehash: 598b35b1bd365e761d8d4c5ef214935e60b971f4
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154024"
---
# <a name="cart-module"></a>Moduł koszyka

[!include [banner](includes/banner.md)]

W tym temacie opisano moduły koszyka i sposób ich dodawania do stron witryny w Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Moduł koszyka wyświetla towary, które zostały dodane do koszyka, zanim odbiorca przejdzie do procesu realizacji transakcji. Ten moduł pokazuje również podsumowanie zamówień i pozwala odbiorcy na zastosowanie lub usunięcie kodów promocyjnych.

Moduł koszyk obsługuje wykonanie transakcji zalogowanych uzytkowników i gości. Ponadto obsługuje łącze **Powrót do zakupów**. Można skonfigurować marszrutę dla tego łącza w **Ustawienia witryny \> Rozszerzenia \> Marszruty**.

Moduł koszyka służy do renderowania danych na podstawie identyfikatora koszyka, który jest plikiem cookie przeglądarki dostępnym w witrynie.

## <a name="cart-module-properties-and-slots"></a>Właściwości modułu koszyka i gniazda

Moduł koszyka ma właściwość **Nagłówka**, która może być ustawiona na wartości takie jak **Torba na zakupy** i **Elementy w koszyku**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduły, których można używać w module koszyka

- **Blok zawartości zaawansowanej** — ten moduł obsługuje obsługę komunikacji niestandardowej w module koszyka. Komunikaty są prowadzone przez system zarządzania zawartością (CMS). Można dodać dowolny komunikat, na przykład „w przypadku problemów z zamówieniem, skontaktuj się z firmą 1-800-Fabrikam”.
- **Wybór sklepu** — ten moduł pokazuje listę magazynów pobliskich, w których dany towar jest dostępny do odebrania. Umożliwia użytkownikom wprowadzenie lokalizacji, w której znajdują się bliskie sklepy. Aby uzyskać więcej informacji na temat tego modułu, należy zapoznać się z tematem [moduł Selector sklepów](store-selector.md).

## <a name="cart-module-settings"></a>Ustawienia modułu koszyka

Moduły koszyka mają następujące ustawienia, które można skonfigurować w **Ustawienia witryny \> Rozszerzenia**:

- **Ilość maksymalna** — To ustawienie jest używane do określania maksymalnej liczby każdej pozycji, którą można dodać do koszyka. Na przykład sprzedawca może zdecydować, że tylko 10 sztuk każdego produktu może być sprzedawanych w jednej transakcji.
- **Sprawdzanie zapasów** — Jeśli wartość jest ustawiona na **prawda**, towar jest dodawany do koszyka dopiero po upewnieniu się, że jest on w zapasach. Ta kontrola zapasów jest realizowana dla scenariuszy, w których towar zostanie wysłany, jak i dla scenariuszy, w których zostanie on odebrany w sklepie. Jeśli wartość jest ustawiona na **fałsz**, nie jest przeprowadzane sprawdzanie zapasów przed dodaniem towaru do koszyka i założenie zamówienia.
- **Bufor zapasów** — ta właściwość służy do określania numeru buforowego zapasów. Zapasy są obsługiwane w czasie rzeczywistym, a w przypadku, gdy wiele odbiorców nakłada zamówienia, może być trudne utrzymywanie dokładnej inwentaryzacji zapasów. Po zakończeniu sprawdzania zapasów, jeśli zapasy są mniejsze niż kwota bufora, produkt jest traktowany jako wychodzący z zapasów. W związku z tym, jeśli sprzedaż będzie się odbywała szybko przez kilka kanałów i inwentaryzacja nie jest w pełni zsynchronizowana, jest mniejsze ryzyko sprzedaży towaru, który jest poza zapasem.
- **Powrót do zakupów** — ta właściwość służy do określania trasy dla łącza **Powrót do zakupów**. Marszrutę można skonfigurować na poziomie witryny, umożliwiając detalistom przejęcie odbiorcy z powrotem na stronę główną lub na inną stronę w witrynie.

## <a name="commerce-scale-unit-interaction"></a>Interakcja Commerce Scale Unit

Moduł koszyka pobiera informacje o produktach za pomocą interfejsów API Commerce Scale Unit. Identyfikator koszyka z pliku cookie przeglądarki jest używany do pobierania wszystkich informacji o produktach z Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Dodawanie modułu koszyka do strony

Aby dodać moduł koszyka do nowej strony i ustawić wymagane właściwości, wykonaj następujące kroki.

1. Utwórz fragment o nazwie **Fragment koszyka** i dodaj moduł koszyka do nowego fragmentu.
1. Dodaj nagłówek do modułu koszyka.
1. Dodaj moduł Wybór sklepu do modułu koszyka.
1. Zapisz fragment, zakończ jego edycję, a następnie go opublikuj.
1. Utwórz szablon o nazwie **Szablon koszyka** i dodaj do niego właśnie utworzony fragment koszyka.
1. Zapisz szablon, zakończ jego edycję, a następnie go opublikuj.
1. Utwórz stronę, która korzysta z nowego szablonu.
1. Zapisz i zobacz podgląd strony.
1. Zakończ edycję strony, a następnie ją opublikuj.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Omówienie zestawu początkowego](starter-kit-overview.md)

[Moduł kontenera](add-container-module.md)

[Moduł wyboru sklepu](store-selector.md)

[Moduł pola zakupu](add-buy-box.md)

[Moduł realizacji transakcji](add-checkout-module.md)

[Moduł potwierdzenia zamówienia](order-confirmation-module.md)

[Moduł nagłówka](author-header-module.md)

[Moduł stopki](author-footer-module.md)
