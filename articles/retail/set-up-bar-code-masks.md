---
title: "Ustawianie masek kodów kreskowych"
description: "W tym temacie opisano, jak konfigurować znaki maski kodów kreskowych i maski kodów kreskowych oraz jak przypisywać maski kodów kreskowych do kodów kreskowych."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 671155cbf76c1570374a1602cd6590117cffa28e
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="set-up-bar-code-masks"></a>Ustawianie masek kodów kreskowych

[!include[banner](includes/banner.md)]


W tym temacie opisano, jak konfigurować znaki maski kodów kreskowych i maski kodów kreskowych oraz jak przypisywać maski kodów kreskowych do kodów kreskowych.

<a name="set-up-bar-code-mask-characters"></a>Konfigurowanie znaków maski kodu kreskowego
-------------------------------

Maski kodów kreskowych są używane do tworzenia kodów kreskowych i do szybkiej identyfikacji kodów kreskowych skanowanych w punkcie sprzedaży (POS). Maski składają się ze znaków, które pełnią rolę symboli zastępczych wskazujących format kodów kreskowych, które zostaną utworzone. Aby skonfigurować maskę kodu kreskowego, należy skonfigurować znaki maski kodu kreskowego. Wybierz kolejno opcje **Handel detaliczny** &gt; **Zarządzanie zapasami** &gt; **Kody kreskowe i etykiety** &gt; **Znaki maski**. Kliknij przycisk **Nowy** i utwórz znaki maski kodu kreskowego. Znaki maski mogą być tworzone w celu wskazywania następujących danych kodu kreskowego:

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Pole**            | **Opis**                                                                                                 |
| **Produkt**          | Symbol zastępczy identyfikatora produktu.                                                                                     |
| **Dowolna liczba**       | Określa liczbę, która będzie trwale zapisywana w kodach kreskowych.                                                  |
| **Cyfra kontrolna**      | Wskazuje, że format kodu kreskowego w masce kodu kreskowego używa cyfry kontrolnej do potwierdzania poprawności kodu kreskowego. |
| **Cyfra rozmiaru**       | Wskazuje rozmiar w kodzie kreskowym utworzonym dla wariantu produktu zawierającego rozmiar.                                 |
| **Cyfra koloru**      | Wskazuje kolor w kodzie kreskowym utworzonym dla wariantu produktu zawierającego kolor.                               |
| **Cyfra stylu**      | Wskazuje styl w kodzie kreskowym utworzonym dla wariantu produktu zawierającego styl.                             |
| **Kod licencji EAN** | Symbol zastępczy licencji EAN wydawanej dla kodów licencji EAN.                                                       |
| **Cena**            | Wskazuje cenę w kodzie kreskowym z osadzoną ceną.                                                                   |
| **Ilość**         | Wskazuje ilość w kodzie kreskowym z osadzoną ilością/losową masą.                                                |
| **Pracownik**         | Wskazuje segment kodu kreskowego dla numeru identyfikacyjnego pracownika używanego w celu logowania się do aplikacji POS za pomocą kodu kreskowego.                                  |
| **Odbiorca**         | Wskazuje segment identyfikatora odbiorcy.                                                                                  |
| **Wprowadzanie danych**       | *Jeszcze nie zaimplementowano.*                                                                                          |
| **Kod rabatu**    | *Wycofane* począwszy od wydania programu Dynamics 365 for Retail z wiosny 2017 r. Uprzednio: Wskazuje kod rabatu dla kodu kreskowego, który jest używany w celu dodawania rabatu do transakcji w punkcie sprzedaży.                                                                   |
| **Kod kuponu**      | Wskazuje kod kuponu w kodzie kreskowym użytym w celu dodania rabatu do zamówienia sieci sprzedaży. Zastępuje kod rabatu.     |
| **Karta upominkowa**        | Wskazuje numer karty upominkowej w przypadku wydawania karty upominkowej lub płacenia taką kartą.                                               |
| **Karta lojalnościowa**     | Dodaje do transakcji odbiorcę zarejestrowanego w programie lojalnościowym i może być używany w trakcie płacenia kartą lojalnościową.                             |

## <a name="define-bar-code-masks"></a>Definiowanie masek kodów kreskowych
Po określeniu znaków wymaganych masek kodów kreskowych wybierz kolejno opcje **Handel detaliczny** &gt; **Zarządzanie zapasami** &gt; **Kody kreskowe i etykiety** &gt; **Ustawienia maski kodów kreskowych**. Na tej stronie można zdefiniować maski kodów kreskowych, które korzystają z wcześniej określonych znaków. Te maski kodów kreskowych będą używane podczas generowania kodów kreskowych i również pomogą identyfikować kody kreskowe skanowane w punkcie sprzedaży.

1.  Kliknij przycisk **Nowy**, aby utworzyć nową maskę kodu kreskowego.
2.  Wprowadź wartości w polach **Identyfikator maski** i **Opis**, a następnie wybierz typ maski kodu kreskowego w polu **Typ**.
3.  W sekcji **Ogólne** wybierz wartość w polu **Standard kodu kreskowego**, a następnie określ prefiks kodu kreskowego, jeśli jest wymagany.
4.  W sekcji **Segment maski kodów kreskowych** dodaj segmenty kodu kreskowy, które będą używane w tworzonym kodzie kreskowym.

Na przykład aby utworzyć maskę kodu kreskowego z identyfikatorem maski „Produkt”, należałoby wykonać następujące czynności:

1.  Utwórz nową maskę kodu kreskowego i wybierz typ „Produkt”.
2.  Wybierz standard kodu kreskowego, na przykład „Kod 39”.
3.  Podaj prefiks, który ma być używany w celu łatwej identyfikacji kodu kreskowego. Na przykład „22”.
4.  Dodaj segment maski. Segment maski „Produkt” zostanie zaznaczony.
5.  Podaj długość segmentu Produkt, na przykład „10”. Długość powinna odpowiadać długości identyfikatora produkt powszechnie używanej w sklepie. Maska będzie wyświetlana jako podgląd w sekcji **Ogólne** w obszarze **Maska**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Przypisywanie masek kodów kreskowych do kodów kreskowych
Aby można było używać masek kodów kreskowych, muszą one zostać przypisane do kodów kreskowych. Kontynuując poprzedni przykład, w celu przypisania maski kodu kreskowego do kodu kreskowego wykonaj następujące czynności:

1.  Wybierz kolejno opcje **Administrowanie organizacją** &gt; **Ustawienia** &gt; **Kody kreskowe**. Kliknij przycisk **Nowy**, aby utworzyć nowy kod kreskowy.
2.  Wprowadź wartości w polach **Konfiguracja** **kodów kreskowych** i **Konfiguracja**.
3.  W sekcji **Ogólne** w polu **Typ kodu kreskowego** zaznacz pozycję „Kod 39”. W polu **Identyfikator** **maski** wybierz utworzoną wcześniej maskę „Produkt”.
4.  W polu **Rozmiar** wpisz „12”.
5.  Kliknij przycisk **Zapisz**.

Teraz można używać maski kodu kreskowego do tworzenia kodów kreskowych dla produktów. Powyższe czynności są przykładowym sposobem tworzenia masek kodów kreskowych dla produktów, ale także ilustrują sposób tworzenia masek kodów kreskowych dla dowolnych obsługiwanych typów kodów kreskowych. Maski, typy i długości kodów kreskowych należy dostosowywać do użytku w swoim konkretnym środowisku.




