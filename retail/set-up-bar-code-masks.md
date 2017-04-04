---
title: "Ustawianie masek kodów kreskowych"
description: "W tym temacie opisano, jak skonfigurować znaki maski kodu kreskowego, maski kodów kreskowych i sposobu przypisywania kodu kreskowego maski do kodów kreskowych."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 265994
ms.assetid: 5831c74d-d2a1-4fa5-9a9a-a5aba8848381
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fe598799d52cacd84da775ac7ace8cf9a30ae5fe
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-code-masks"></a>Ustawianie masek kodów kreskowych

W tym temacie opisano, jak skonfigurować znaki maski kodu kreskowego, maski kodów kreskowych i sposobu przypisywania kodu kreskowego maski do kodów kreskowych.

<a name="set-up-bar-code-mask-characters"></a>Konfigurowanie znaków maski kodu kreskowego
-------------------------------

Maski kodu kreskowego są używane do tworzenia kodów kreskowych i szybką identyfikację kodów kreskowych, które są skanowane w punkcie sprzedaży (POS). Maski składa się z znaków, które pełnią rolę elementów zastępczych, które wskazują format dla kodów kreskowych, które zostaną utworzone. Aby skonfigurować maskę kodu kreskowego, musisz skonfigurować znaki maski kodu kreskowego. Przejdź do **sieci sprzedaży i handlu**&gt;**Zarządzanie zapasami**&gt;**kody kreskowe i etykiety**&gt;**znaki maski**. Kliknij **nowy** Aby utworzyć znaki maski kodu kreskowego. Znaki maski mogą być tworzone do wskazania następujących danych kodu kreskowego.

|                      |                                                                                                                 |
|----------------------|-----------------------------------------------------------------------------------------------------------------|
| **Field**            | **Description**                                                                                                 |
| **Product**          | Symbol zastępczy dla identyfikatora produktu.                                                                                     |
| **Any number**       | Można określić liczbę, która będzie trudno kodowane w kodów kreskowych.                                                  |
| **Check digit**      | Wskazuje, że format kodu kreskowego w masce kodu kreskowego używa cyfrę kontrolną, aby potwierdzić poprawność kodu kreskowego. |
| **Size digit**       | Wskazuje rozmiar w kodzie kreskowym, utworzony dla wariantu produktu, który zawiera rozmiar.                                 |
| **Color digit**      | Wskazuje kolor w kodzie kreskowym, utworzony dla wariantu produktu, który zawiera kolor.                               |
| **Style digit**      | Wskazuje styl w kodzie kreskowym, utworzony dla wariantu produktu, który zawiera styl.                             |
| **EAN license code** | Symbol zastępczy dla licencji EAN wydane dla kodów licencji EAN.                                                       |
| **Cena**            | Oznacza cenę dla ceny embedded kodów kreskowych.                                                                   |
| **Quantity**         | Wskazuje ilość w ilości/losowo wagi osadzone kody kreskowe.                                                |
| **Employee**         | Wskazuje segmentu kodu kreskowego dla używany do logowania się kod kreskowy POS numer identyfikacyjny pracownika.                                  |
| **Customer**         | Wskazuje segment Identyfikatora klienta.                                                                                  |
| **Wprowadzanie danych**       | *Jeszcze nie zaimplementowano.*                                                                                          |
| **Discount code**    | Wskazuje kod rabatu dla kodu kreskowego, który jest używany do dodawania Rabat do punktu transakcji sprzedaży             |
| **Karta upominkowa**        | Wskazuje numer karty upominkowej przy wydawaniu lub płatności kartą upominkową.                                               |
| **Loyalty card**     | Dodaje karty lojalnościowej do transakcji i może być używany, gdy płatność za lojalność.                             |

## <a name="define-bar-code-masks"></a>Definiowanie maski kodów kreskowych
Po znaki maski kodu kreskowego są określone dla maski kodu kreskowego konieczne, przejdź do **sieci sprzedaży i handlu**&gt;**Zarządzanie zapasami**&gt;**kody kreskowe i etykiety**&gt;**ustawienia maski kodów kreskowych**. Na tej stronie można zdefiniować maski kodów kreskowych, które korzystają z wcześniej określonych znaków. To bar kod maski będzie używana podczas generowania kodów kreskowych i będzie również pomaga zidentyfikować kodów kreskowych skanowane w punkcie sprzedaży.

1.  Kliknij **nowy** Aby utworzyć nową maskę kodu kreskowego.
2.  Wpisz wartości w **Identyfikatora maski** i **opis** pola, a następnie wybierz typ maski kodu kreskowego **typu** pole.
3.  W **ogólne** sekcji, wybierz wartość w **standardowy kod kreskowy** w polu, a następnie określ prefiks kodu kreskowego, jeśli jest ono wymagane.
4.  W **segment maski kodów kreskowych** sekcji, dodać kod kreskowy segmentów, które będą używane w kodzie kreskowym ma zostać utworzony.

Na przykład do utworzenia maski kodu kreskowego z Identyfikatora maski "Produkt", można by wykonaj następujące czynności:

1.  Utworzyć nową maskę kodu kreskowego i wybierz typ "Produkt".
2.  Wybierz standard kodu kreskowego, na przykład "Code 39".
3.  Podać prefiks umożliwia łatwą identyfikację kodu kreskowego. Na przykład "22".
4.  Dodaj segment maski. Segment maski "Produkt" będzie zaznaczone.
5.  Podać długość segmentu produktu, na przykład "10". Długość powinna odpowiadać długość Identyfikatora produkt, często używane w magazynie. Maska będzie wyświetlany jako podgląd w **ogólne** sekcji w obszarze **maski**.

## <a name="assign-bar-code-masks-to-bar-codes"></a>Przypisywanie maski kodów kreskowych do kodów kreskowych
Maski kodów kreskowych musi być przypisany do kodów kreskowych, zanim będą mogły być użyte. W poprzednim przykładzie kontynuowanie przypisać maski kodu kreskowego do kodu kreskowego, wykonaj następujące czynności:

1.  Przejdź do **Administrowanie organizacją**&gt;**instalacji**&gt;**kodów kreskowych**. Kliknij **nowy** Aby utworzyć nowy kod kreskowy.
2.  Wpisz wartości w **kodu kreskowego****instalacji** i ** Instalator ** pól.
3.  W **ogólne** sekcji w **typu kodu kreskowego** wybierz "Code 39". W **maski****ID** wybierz maskę "Produkt" utworzone wcześniej.
4.  Pod **rozmiar**, wprowadź "12".
5.  Click **Save**.

Do tworzenia kodów kreskowych dla produktów można teraz maski kodu kreskowego. Powyższe czynności są przykładami sposobu tworzenia maski kodu kreskowego dla produktów, ale także ilustrować sposób tworzenia maski kodu kreskowego dla dowolnego typu kodu kreskowego obsługiwane. Maski kodów kreskowych, typów i długości powinny być dostosowane do użytku w określonym środowisku.


