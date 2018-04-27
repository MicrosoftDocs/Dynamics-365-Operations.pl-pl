---
title: "Konfigurowanie układów ekranu dla aplikacji punktu sprzedaży"
description: "Ten temat zawiera informacje dotyczące układów ekranu dla aplikacji Microsoft Dynamics 365 for Retail Point of Sale (POS)."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ad425ab0848ab04003b7378cb5c488650f01c441
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="configure-screen-layouts-for-pos"></a>Konfigurowanie układów ekranu dla punktu sprzedaży

[!INCLUDE [banner](includes/banner.md)]

Ten temat zawiera informacje dotyczące układów ekranu dla aplikacji Microsoft Dynamics 365 for Retail Point of Sale (POS).

Interfejs użytkownika programu Microsoft Dynamics 365 for Retail Point of Sale (POS) można konfigurować przy użyciu kombinacji profili graficznych i układów ekranu, które się przypisuje do sklepów, kas i/lub użytkowników.

## <a name="visual-profile"></a>Profil graficzny
Profile graficzne są przypisywane do kas i używane do określania elementów wizualnych, które są specyficzne dla kas i wspólne dla użytkowników. Każdy użytkownik, który się loguje do kasy, będzie widział ten sam motyw, kolory i obrazy. 

**Numer profilu** — Numer profilu jest unikatowym identyfikatorem profilu graficznego. 

**Opis** — Opis pozwala wprowadzić znaczącą nazwę, która pomoże identyfikować profil odpowiedni w danej sytuacji.

**Motyw** — Użytkownicy mogą wybierać między motywami aplikacji Jasny i Ciemny. Te ustawienia wpływają na kolory czcionki i tła całej aplikacji.

**Kolor akcentu** — Kolor akcentu jest używany w całej aplikacji POS do odróżniania lub wyróżniania pewnych elementów wizualnych, takich jak kafelki, przyciski poleceń i hiperłącza. Zazwyczaj te elementy wykonują różne akcje.

**Kolor nagłówka** — Kolor nagłówka pozwala użytkownikowi skonfigurować kolor nagłówka strony zgodnie z identyfikacją wizualną sprzedawcy detalicznego. Ta funkcja jest dostępna tylko w programie Dynamics 365 for Retail w wersji 1611.

**Tło logowania** — Użytkownicy mogą określić obraz tła dla ekranu logowania. Rozmiary plików obrazów tła powinny być jak najmniejsze, ponieważ przechowywanie i ładowanie dużych plików może mieć negatywny wpływ na szybkość działania i zachowanie aplikacji.

**Tło aplikacji** — Aplikacja POS można również jako tła w swoich wszystkich oknach używać obrazu zamiast jednolitego koloru motywu. Podobnie jak w przypadku teł logowania, zaleca się stosować jak najmniejsze rozmiary plików.

## <a name="screen-layouts"></a>Układy ekranu
Konfiguracja układu ekranu decyduje o akcjach, zawartości i położeniu formantów interfejsu użytkownika na ekranie powitalnym i ekranie transakcji w aplikacji punktu sprzedaży. 

**Ekran powitalny** — W większości przypadków ekran powitalny to strona, którą użytkownicy widzą podczas pierwszego logowania do aplikacji punktu sprzedaży. Ekran powitalny może zawierać obraz identyfikacyjny marki oraz siatki przycisków umożliwiające dostęp do operacji w punkcie sprzedaży. Zwykle w tym miejscu umieszcza się operacje, które nie są specyficzne dla bieżącej transakcji. 

**Ekran transakcji** — Ekran transakcji jest w aplikacji punktu sprzedaży głównym ekranem do przetwarzania transakcji i zamówień sprzedaży. Ekran transakcji można skonfigurować przy użyciu projektanta układu ekranu. 

**Domyślny ekran startowy** — Niektórzy sprzedawcy detaliczni wolą, aby kasjer po zalogowaniu przechodził bezpośrednio do ekranu transakcji. Ustawienie domyślnego ekranu startowego pozwala użytkownikom ustawić takie zachowanie dla każdego układu ekranu.

### <a name="assignment"></a>Przypisanie

Układy ekranów można przypisywać na poziomie sklepu, kasy lub użytkownika. Przypisanie użytkownikowi zastępuje przypisanie do kasy i sklepu, a przypisanie na poziomie kasy ma priorytet nad przypisaniem do sklepu. W prostym scenariuszu, gdzie wszyscy użytkownicy korzystają z tego samego układu niezależnie od kasy ani roli, układ ekranu można ustawić tylko na poziomie sklepu. W przypadkach, gdy niektóre kasy lub użytkownicy wymagają specjalnych układów, można je przypisywać indywidualnie.

### <a name="layout-sizes"></a>Rozmiary układów

Ta funkcja ma zastosowanie tylko do programu Dynamics 365 for Retail w wersji 1611. Ponieważ w wielu przypadkach układy ekranu mogą być używane w wielu rozmiarach i rozdzielczościach ekranu, użytkownicy mogą konfigurować układ i zawartość dla każdego ekranu. Aplikacji punktu sprzedaży będzie automatycznie wybierać najbliższy rozmiar układu dla urządzenia w momencie uruchamiania. Układ ekranu może również zawierać konfiguracje dla urządzeń pełnoekranowych i kompaktowych. Ta konfiguracja pozwala przypisać użytkownika do jednego układu ekranu, który będzie działał w urządzeniach o różnych rozmiarach i typach znajdujących się w sklepie. 

**Modern POS - Pełna wersja** — Pełne układy zazwyczaj najlepiej nadają się do większych ekranów, takich jak w monitorach komputerowych i tabletach. Użytkownicy mogą wybierać elementy interfejsu użytkownika, które mają się znaleźć w układach, określać ich rozmiar i położenie oraz konfigurować ich szczegółowe właściwości. Układy pełne obsługują konfiguracje poziome i pionowe. 

**Modern POS - Wersja kompaktowa** — Układy kompaktowe zazwyczaj najlepiej nadają się do telefonów lub małych tabletów. Możliwości projektowania są ograniczone do urządzeń kompaktowych. Użytkownicy mogą konfigurować kolumny i pola okienek pokwitowania i sum.

### <a name="screen-layout-designer"></a>Projektant układu ekranu

Każdy rozmiar układu w układzie ekranu musi być skonfigurowany przy użyciu projektanta układu ekranu. Projektant umożliwia użytkownikom określanie i konfigurowanie elementów interfejsu użytkownika ekranu transakcji. Projektant układu ekranu używa funkcji ClickOnce, aby pobrać, zainstalować i uruchomić najnowszą wersję aplikacji za każdym razem, gdy użytkownik uzyskuje do niej dostęp. Koniecznie sprawdź wymagania funkcji ClickOnce dotyczące przeglądarek — niektóre przeglądarki, taka jak Chrome, wymagają rozszerzeń. 

**Klawiatura numeryczna** — Klawiatura numeryczna jest głównym narzędziem wprowadzania danych przez użytkownika na ekranie transakcji w aplikacji punktu sprzedaży. Można ją skonfigurować tak, aby była pokazywana cała klawiatura ekranowa, co jest idealnym rozwiązaniem dla ekranów dotykowych, lub tylko pole wprowadzania danych, którego można używać w połączeniu z klawiaturą fizyczną. Ustawienia klawiatury numeryczne są dostępne tylko w pełnym układzie. W programie Dynamics 365 for Retail w wersji 1611 układy kompaktowe zawsze mają dostępną pełną klawiaturę numeryczną na ekranie transakcji.

**Panel sum** — Panel sum można skonfigurować na jedną lub dwie kolumny pokazujące pola takie jak liczba wierszy, kwota rabatu, opłaty, suma częściowa i podatek. W programie Dynamics 365 for Retail w wersji 1611 układy kompaktowe obsługują tylko pojedyncze kolumny sum. 

**Pokwitowanie** — Panel pokwitowania zawiera wiersze sprzedaży, wiersze płatności oraz informacje o dostawie produktów i usług przetwarzanych w aplikacji punktu sprzedaży. Użytkownicy mogą określać kolumny, szerokości i położenie. W układach kompaktowych w programie Dynamics 365 for Retail w wersji 1611 można również skonfigurować dodatkowe informacje, które będą wyświetlane w wierszu poniżej głównego wiersza. 

**Karta odbiorcy** — Karta odbiorcy pokazuje informacje odnoszące się do odbiorcy aktualnie skojarzonego z transakcją. Kartę odbiorcy można skonfigurować tak, aby ukrywała lub pokazywała dodatkowe informacje. 

**Formant karty** — Formant karty można umieścić na układzie ekranu, a następnie wewnątrz niej umieścić inne formanty, na przykład klawiatury numerycznej, karty odbiorcy lub siatek przycisków. Formant karty jest kontenerem, który pomaga użytkownikom zmieścić więcej zawartości na ekranie. Formant karty jest dostępny tylko w pełnych układach. 

**Obraz** — Formant obrazu może służyć do wyświetlania logo sklepu lub innego obrazu identyfikacyjnego marki na ekranie transakcji. Formant obrazu jest dostępny tylko w pełnych układach. 

**Rekomendowane produkty** — Jeśli formant rekomendowanych produktów zostanie skonfigurowany dla środowiska, będzie wyświetlał sugestie produktów przy użyciu mechanizmu uczenia maszynowego. Formant rekomendowanych produktów jest dostępny tylko w pełnych układach w programie Dynamics 365 for Retail w wersji 1611. **Formant niestandardowy**— Formant niestandardowy pełni rolę symbolu zastępczego w układzie ekranu, pozwalając użytkownikom rezerwować miejsce na niestandardową zawartość. Formant niestandardowy jest dostępny tylko w pełnych układach.

<a name="see-also"></a>Informacje dodatkowe
--------

[Instalowanie projektanta układu programu Retail POS](install-pos-layout-designer.md)




