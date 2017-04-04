---
title: "Szablony paragonów i drukowanie"
description: "W tym artykule opisano modyfikowanie układów formularzy w celu sterowania sposobem drukowania paragonów, faktur i innych dokumentów. Microsoft Dynamics 365 dla operacji - handel detaliczny zawiera konstruktora układu formularza, który można łatwo tworzyć i modyfikować różnego rodzaju układy formularzy."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 57841
ms.assetid: e530dd8e-95e2-4021-90bd-ce1235f9e250
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fabaacbc7187b38a1745c2139a9eb7760f2be987
ms.lasthandoff: 03/31/2017


---

# <a name="receipt-templates-and-printing"></a>Szablony paragonów i drukowanie

W tym artykule opisano modyfikowanie układów formularzy w celu sterowania sposobem drukowania paragonów, faktur i innych dokumentów. Microsoft Dynamics 365 dla operacji - handel detaliczny zawiera konstruktora układu formularza, który można łatwo tworzyć i modyfikować różnego rodzaju układy formularzy.

**Ważne:** należy skonfigurować układy formularzy i przychodu profile, aby drukować paragony i inne dokumenty z Retail POS nowoczesnych i POS chmury. Może zawierać wiele układów formularzy w profilu paragonów. Następnie można przypisać profil paragonu do drukarki, modyfikując profil sprzętu.

## <a name="set-up-a-receipt-format"></a>Konfigurowanie formatu paragonów
1.  Kliknij **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**POS**&gt;**formaty paragonu**.
2.  Na stronie **Format paragonu** kliknij opcję **Nowy**, aby utworzyć nowy układ paragonu lub wybrać istniejący układ.
3.  W polu **Format paragonu** wprowadź identyfikator układu formularza, a następnie wybierz typ paragonu, dla którego będzie używany ten układ. Można także wprowadzić opis i krótką nazwę paragonu w polu **Tytuł**.
4.  Na skróconej karcie **Ogólne** wybierz odpowiednią opcję, aby zdefiniować zachowanie drukarki:
    -   **Zawsze drukuj** — paragon jest drukowany automatycznie, zgodnie z potrzebą.
    -   **Nie Drukuj** — paragon nie jest drukowany.
    -   **Monituj użytkownika** — użytkownik jest proszony o wydrukowanie paragonu.
    -   **Zgodnie z wymogami** — ta opcja jest używana tylko dla paragonów za upominek. Gdy ta opcja jest zaznaczona, użytkownik może drukować paragon ze strony **zmiany**, jeśli paragon za upominek jest wymagany.

## <a name="design-a-receipt-format"></a>Projektowanie formatu paragonu
Użyj konstruktor układu formularza, aby w sposób graficzny stworzyć układ formularza dokumentu. Strona **Projektant formatu paragonu** zawiera trzy części: **Nagłówek**, **Wiersze** i **Stopka**. Niektóre typy układu formularza używają elementów ze wszystkich trzech sekcji, natomiast inne typy elementów tylko z jednej lub z dwóch części. Aby wyświetlić elementy, które są dostępne dla każdej sekcji, kliknij odpowiedni przycisk w okienku nawigacji po lewej stronie strony.

1.  Kliknij **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**Instalator POS**&gt;**POS**&gt;**formaty paragonu**.
2.  Na stronie **formatu paragonu** wybierz układ formularza, a następnie kliknij przycisk **Projektant**.
3.  Kliknij **Uruchom**, aby rozpocząć instalację hosta projektanta sieci sprzedaży.
4.  Na pasku powiadomień, który pojawia się u dołu okna programu Internet Explorer, kliknij przycisk **Otwórz**, aby rozpocząć instalację projektanta obsługiwanego jednym kliknięciem. (Na pasku powiadomień może pojawiają się w innym miejscu w innych przeglądarkach). Wskaźnik postępu pokazuje postęp procesu instalacji.
5.  Po zakończeniu instalacji, wprowadź swój 365 Dynamics dla operacji nazwę użytkownika i hasło, a następnie kliknij **logowania** uruchomić projektanta.
6.  Po zweryfikowaniu poświadczeń użytkownika i uruchomieniu projektanta można rozpocząć projektowanie formatu paragonów lub zmodyfikować istniejący format.
7.  Aby utworzyć elementy formularza, zaznacz sekcje **Nagłówek**, **Wiersze** lub **Stopka**, a następnie przeciągnij element z sekcji do obszaru roboczego. Większość elementów zawiera zmienne, które są automatycznie wypełnione danymi z bazy danych. Inne elementy, na przykład **Tekst**, umożliwiają drukowanie na paragonie niestandardowego tekstu. **Uwaga:**Liczbę wierszy każdej sekcji można określić za pomocą liczby w prawym dolnym rogu sekcji. Aby ułatwić sobie modyfikowanie sekcji, zwiększ jej wysokość, przeciągając pasek zmiany rozmiaru u dołu sekcji. Wysokość sekcji na obszarze roboczym nie wpływa na liczbę wierszy rzeczywistego paragonu.
8.  Po przeciągnięciu elementu do obszaru roboczego ustaw właściwości dla części w okienku **Informacje o obiekcie** na dole strony. Wprowadź jedno lub więcej z następujących ustawień:
    -   **Wyrównaj** — umożliwia ustawienie wyrównania pola jako **Do lewej** lub **Do prawej**.
    -   **Znak wypełniający** — umożliwia określenie znaku odstępu. Domyślnie jest używane puste miejsce, ale można wprowadzić dowolny znak.
    -   **Prefiks** — umożliwia wpisanie wartości, która ma pojawiać się na początku pola. To ustawienie dotyczy tylko elementu **Wiersze **układu.
    -   **Znaki** — umożliwia określenie maksymalnej liczby znaków w polu, jeśli element zawiera zmienną. Jeśli tekst w tym polu jest dłuższy niż liczba znaków, którą określisz, tekst jest obcięty do rozmiaru pola.
    -   **Zmienna** — jeśli element zawiera zmienną i nie można go dostosować, to pole wyboru jest zaznaczane automatycznie.
    -   **Typ czcionki **— można ustawić styl czcionki **Zwykła** lub **Pogrubiona**. Litery pogrubione zajmują dwa razy więcej miejsca niż normalne. Dlatego niektóre znaki mogą zostać obcięte.
    -   **Usuń** — ten przycisk należy kliknąć, aby usunąć zaznaczony element z układu formularza.

## <a name="assign-receipt-profiles"></a>Przypisywanie profili paragonów
Profile paragonów są przypisywane bezpośrednio do drukarki za pomocą profilu sprzętu.

1.  Otwórz profil sprzętu, klikając **sieci sprzedaży i handlu**&gt;**konfigurację kanału**&gt;**konfiguracji punktu sprzedaży**&gt;**profile POS**&gt;**profilu sprzętu**.
2.  Wybierz drukarkę, a następnie w polu **profilu paragonów ** przypisz profil paragonu do użycia w rejestrze.

**Uwaga:** Jeśli używane są dwie drukarki, jedna drukarka może służyć do standardowych 40-kolumnowych paragonów. Druga drukarka jest zwykle używana do drukowania paragonów pełnostronicowych, które muszą zawierać więcej informacji. Paragony te uwzględniają paragony do zamówienia sprzedaży odbiorcy i faktury odbiorcy.


