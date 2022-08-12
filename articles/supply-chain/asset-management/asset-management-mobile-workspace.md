---
title: Używanie mobilnego obszaru roboczego zarządzania składnikami majątku
description: Ten artykuł zawiera informacje o mobilnym obszarze roboczym Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.dyn365.ops.version: 10.0.5
ms.search.validFrom: 2019-08-31
ms.openlocfilehash: 8f215d5f6758f222a9dc6b382b172009836547ec
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067010"
---
# <a name="use-the-asset-management-mobile-workspace"></a>Używanie mobilnego obszaru roboczego zarządzania składnikami majątku

[!include [banner](../../includes/banner.md)]
[!include [mobile app deprecated](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Ten artykuł zawiera informacje o mobilnym obszarze roboczym **Zarządzanie składnikami majątku**. Ten obszar roboczy umożliwia użytkownikom wyświetlanie i tworzenie żądań konserwacji i zleceń pracy. Użytkownicy mogą również wyświetlać przypisane zadania dotyczące zleceń pracy w widoku kalendarza lub listy. Można również wyświetlać i wyszukiwać zasoby i lokalizacje czynności konserwacyjnych.

## <a name="overview"></a>Przegląd

Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania składnikami majątku i zadań zleceń pracy w Dynamics 365 Supply Chain Management. Mobilny obszar roboczy **Zarządzania składnikami majątku** umożliwia użytkownikom szybkie przeglądanie przydzielonych zadań zlecenia produkcyjnego na wybranym urządzeniu przenośnym. Użytkownicy mogą również tworzyć i zarządzać żądaniami konserwacji, aktualizować stan cyklu życia oraz wyświetlać szczegóły dotyczące składników majatku i lokalizacji czynności konserwacyjnych przy użyciu urządzeń przenośnych.

W szczególności mobilny obszar roboczy **Zarządzanie składnikami majatku** pozwala użytkownikom wykonywać następujące zadania:

- Umożliwia tworzenie, wyświetlanie i edytowanie żądań konserwacji, sporządzanie fotografii lub dołączanie istniejącego obrazu do żądania konserwacji, zmiana stanu cyklu obsługi żądania konserwacji. 
- Umożliwia tworzenie, wyświetlanie i edytowanie zleceń pracy, sporządzanie fotografii lub dołączanie istniejącego obrazu do zlecenia pracy, zmiana stanu cyklu obsługi zlecenia pracy, wyświetlanie zadań zlecenia pracy.
- Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza.
- Służy do tworzenia, wyświetlania i edytowania zadania zlecenia pracy, aktualizowania liczników składników majątku, wyświetlania listy kontrolnej konserwacji, wyświetlania i edytowania notatek o zadaniach zleceń pracy, wyświetlania narzędzi wymaganych dla zadania zlecenia pracy.
- Służy do wyświetlania lub wyszukiwania określonego składnika majątku lub lokalizacji czynności konserwacyjnych.

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było używać mobilnego obszaru roboczego **Zarządzanie składnikami majątku**, administrator musi skonfigurować wymagane konta użytkowników i pracowników i opublikować obszar roboczy. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie mobilnego obszaru roboczego Zarządzanie składnikami majątku](set-up-asset-management-mobile.md).

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobierz i zainstaluj mobilne aplikacje finansowe i operacyjne (Dynamics 365):

- [Telefony Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Telefony iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Logowanie do aplikacji mobilnej

1. Uruchom aplikację na urządzeniu komórkowym.

1. Wprowadź adres URL usługi Dynamics 365.

1. Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.

1. Po zalogowaniu się zobaczysz obszary robocze dostępne dla firmy. Należy zauważyć, że jeśli administrator systemu później opublikuje nowy obszar roboczy, należy odświeżyć listę mobilnych obszarów roboczych.

    ![Wybieranie obszaru roboczego.](media/am-mobile-01.png "Wybieranie obszaru roboczego")

## <a name="view-assigned-work-order-jobs-in-calendar-view"></a>Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Kalendarz zadań zlecenia pracy**

1. Wybierz datę, dla której mają zostać wyświetlone zadania zlecenia pracy. Na liście widoczny jest identyfikator składnika majatku i identyfikator lokalizacji czynności konserwacyjnych dla każdego zadania zlecenia produkcyjnego.

1. Wybierz zadanie zlecenia pracy na liście, aby wyświetlić szczegóły zadania: szczegóły dotyczące składnika majątku i lokalizacji czynności konserwacyjnych oraz inne łącza nawigacji, które umożliwiają wyświetlanie **Załączników**, **List kontrolnych**, **Narzędzi**, **Liczników składników majatku**, **Notatek**, **Arkuszy**.

    ![Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza.](media/am-mobile-02.png "Umożliwia wyświetlenie przypisanych zadań zlecenia pracy w widoku kalendarza")

## <a name="create-a-work-order-job"></a>Tworzenie zadania zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy, dla którego chcesz utworzyć nowe zadanie zlecenia pracy.

1. Wybierz przycisk **Dodaj wiersz**.

1. Wybierz **Składnik majątku**, dla którego chcesz utworzyć nowe zadanie zlecenia pracy.

1. Wybierz **Typ zadania konserwacji**, **Wariant typu zadania konserwacji** i **Profesja**.

1. Wybierz opcję **Gotowe**.

    ![Ekran dodawania wiersza.](media/am-mobile-03.png "Ekran dodawania wiersza")


## <a name="add-attachment-to-a-work-order-job"></a>Dodawanie załącznika do zadania zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz dodać załącznik.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **Szczegóły zadania zlecenia pracy**.

1. Wybierz **Załączniki** na stronie **Szczegóły zadania zlecenia pracy**.

1. Zostaną wyświetlone istniejące załączniki dla zadania zlecenia pracy Wybierz **Dodaj załącznik**.

1. Wprowadź **Nazwę** i **Notatki** dotyczące załącznika.

1. Wybierz **Wybierz obraz**, aby wybrać zdjęcie z galerii mobilnej, lub **Zrób zdjęcie**, aby zrobić zdjęcie.

1. Wybierz opcję **Gotowe**.

    ![Wyświetlanie i dodawanie załączników do zadania zlecenia pracy.](media/am-mobile-04.png "Wyświetlanie i dodawanie załączników do zadania zlecenia pracy")

## <a name="view-maintenance-checklist-on-a-work-order-job"></a>Przeglądanie listy kontrolnej konserwowanego składnika majątku w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć listę kontrolną.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

1. Wybierz **Listy kontrolne** na stronie **Szczegóły zadania zlecenia pracy**.

1. Zostanie wyświetlona lista wierszy listy kontrolnej powiązanych z zadaniem zlecenia pracy. Wybierz wiersz listy kontrolnej w celu wyświetlenia **Instrukcji** i dodania **Notatek**.

1. Kliknij przycisk wstecz (**<**), aby wrócić do poprzedniej strony.

    ![Lista kontrolna konserwowanego składnika majątku i szczegóły wiersza.](media/am-mobile-05.png "Lista kontrolna konserwowanego składnika majątku i szczegóły wiersza")

## <a name="view-and-update-asset-counters-on-a-work-order-job"></a>Wyświetlanie i aktualizowanie liczników składników majątku w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć licznik składników majątku.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

1. Wybierz **Liczniki składników majątku** na stronie **Szczegóły zadania zlecenia pracy**.

1. Zostanie wyświetlona lista liczników składników majątku powiązanych z zadaniem zlecenia pracy. Wybierz ikonę ołówek w wierszu licznika składników majątku, aby zaktualizować wartość licznika.

1. Wprowadź nową wartość licznika i wybierz **Gotowe**.

    ![Wyświetlanie i aktualizowanie liczników składnika majątku.](media/am-mobile-06.png "Wyświetlanie i aktualizowanie liczników składnika majątku")

## <a name="register-consumption-on-a-work-order-job"></a>Rejestrowanie zużycia w zadaniu zlecenia pracy

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy > zadanie zlecenia pracy, dla którego chcesz zobaczyć rejestrację zużycia.
    - Można również wybrać folder **Kalendarz zadań zlecenia pracy** lub listę **Lista zadań zleceń pracy** na stronie głównej, aby przejść do strony **szczegóły zadania zlecenia pracy**.

1. Wybierz **Arkusze** na stronie **Szczegóły zadania zlecenia pracy**.

1. Wybierz opcję **Dodaj godziny**, aby utworzyć rejestracje godzin pracy.
    1. Wybierz **Kategoria** w polu wyszukiwania.
    1. W polu **Godziny** wprowadź liczbę godzin pracy, jaka przypada na zadanie zlecenia pracy.
    1. Wybierz odpowiednią **Właściwość wiersza**.
    1. Wybierz opcję **Gotowe**.

1. Wybierz opcję **Dodaj pozycje**, aby utworzyć rejestracje pozycji.
    1. Wybierz **Kod towaru** w polu wyszukiwania.
    1. Wybierz **Lokalizacja** w polu wyszukiwania.
    1. Wprowadź **Ilość** zużytych towarów.
    1. Wybierz opcję **Gotowe**.

1. Wybierz opcję **Dodaj wydatek**, aby utworzyć rejestracje wydatków.
    1. Wybierz **Kategoria** w polu wyszukiwania.
    1. Umożliwia wprowadzenie ilości dla rejestracji wydatków.
    1. Wybierz **Waluta sprzedaży** w polu wyszukiwania.
    1. Umożliwia wprowadzenie **Kosztu własnego** dla rejestracji wydatków.
    1. Wybierz opcję **Gotowe**.

    ![Aktualizowanie arkusza zlecenia pracy.](media/am-mobile-07.png "Aktualizowanie arkusza zlecenia pracy")

## <a name="update-lifecycle-state-on-a-work-order"></a>Aktualizuj stan cyklu życia zlecenia pracy.

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie zlecenia pracy dotyczące koserwacji**.

1. Wybierz zlecenie pracy, dla którego chcesz aktualizować stan cyklu życia.

1. Wybierz przycisk **Aktualizuj stan** w dolnej części ekranu.

1. Wybierz nowy stan cyklu życia z listy.

1. Wybierz opcję **Gotowe**.

    ![Aktualizuj stan cyklu życia zlecenia pracy.](media/am-mobile-08.png "Aktualizuj stan cyklu życia zlecenia pracy.")

## <a name="create-a-maintenance-request"></a>Tworzenie żądania konserwacji

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie żądania konserwacji**.

1. Wybierz **Akcje** u dołu ekranu i wybierz opcję **Utwórz żądanie konserwacji**.

1. Jeśli dla żądań konserwacji w module **Zarządzanie składnikami majątku** jest włączona sekwencja numerów, pole **Żądanie konserwacji** jest ukryte, ponieważ jest ono wypełniane automatycznie. Jeśli pole **Żądanie konserwacji** jest widoczne, należy wprowadzić identyfikator żądania konserwacji.

1. Wybierz **Typ żądania konserwacji**.

1. Wprowadź **Opis** żądania konserwacji.

1. Wybierz **Składnik majątku**, dla którego mają być tworzone żądania.

1. Wybierz **Poziom usług** dla żądania konserwacji.

1. Wybierz opcję **Gotowe**.

    ![Tworzenie żądania konserwacji.](media/am-mobile-09.png "Tworzenie żądania konserwacji")

## <a name="add-attachment-to-a-maintenance-request"></a>Dodaj załącznik do żądania konserwacji

1. Na urządzeniu przenośnym otwórz obszar roboczy **Zarządzanie składnikami majątku**.

1. Wybierz **Wszystkie żądania konserwacji**.

1. Wybierz żądanie konserwacji, do którego chcesz dodać załącznik.

1. Wybierz **Załączniki** w dolnej części ekranu.

1. Wybierz **Dodaj załączniki**.

1. Wprowadź **Nazwę** i **Notatki** dotyczące załącznika.

1. Wybierz **Wybierz obraz**, aby wybrać zdjęcie z galerii mobilnej, lub **Zrób zdjęcie**, aby zrobić zdjęcie.

1. Wybierz opcję **Gotowe**.

    ![Dodawanie załącznika do żądania konserwacji.](media/am-mobile-10.png "Dodawanie załącznika do żądania konserwacji")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

