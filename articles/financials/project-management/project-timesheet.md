---
title: Aplikacja mobilna Project timesheet
description: Ten temat zawiera informacje dotyczące aplikacji mobilnej Microsoft Dynamics 365 Project Timesheet. Aplikacja mobilna Project timesheet umożliwia użytkownikom przesyłanie i zatwierdzanie kart czasu dla projektów na urządzeniach mobilnych.
author: abruer
manager: AnnBe
ms.date: 04/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: josaw1
ms.dyn365.ops.version: 10
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: a475085001b8fa10814c864ef35129eb6ebfdfef
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1529886"
---
# <a name="microsoft-dynamics-365-project-timesheet-mobile-application"></a>Aplikacja mobilna Microsoft Dynamics 365 Project Timesheet

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Przegląd

Aplikacja mobilna Microsoft Dynamics 365 Project Timesheet umożliwia użytkownikom przesyłanie i zatwierdzanie kart czasu dla projektów na urządzeniach mobilnych (iPhone lub Android). Ta aplikacja udostępnia funkcję karty czasu pracy znajdującą się w obszarach zarządzania projektem i księgowania systemu Microsoft Dynamics 365 for Finance and Operations, poprawiając wydajność i efektywność, a także umożliwiając punktualne wprowadzanie i zatwierdzanie kart czasu pracy.

## <a name="download-and-install-the-mobile-app"></a>Pobieranie i instalowanie aplikacji mobilnej

Pobierz i zainstaluj aplikację mobilną Microsoft Dynamics 365 Project Timesheet na telefony z systemem Android lub iPhone ze sklepu z aplikacjami mobilnymi na Twoje urządzenie.

## <a name="enable-the-app"></a>Włącz aplikację 

W Dynamics 365 for Finance and Operations aplikacja mobilna Project Timesheet musi być włączona. Aby włączyć tę funkcję, przejdź do menu **Parametry modułu Zarządzanie projektami i ich księgowanie \> Karta czasu pracy** i wybierz parametr **Włącz Microsoft Dynamics 365 Project Timesheet**.

## <a name="sign-in-to-the-app"></a>Zaloguj się do aplikacji

1.  Uruchom aplikację na urządzeniu komórkowym.

2.  Wprowadź swój adres URL w usłudze Microsoft Dynamics 365 for Finance and Operations.

3.  Podczas pierwszego logowania pojawi się monit o podanie nazwy użytkownika i hasła. Wprowadź swoje poświadczenia.

4.  System zaloguje Cię do Twojej domyślnej firmy.

## <a name="submit-a-project-timesheet"></a>Prześlij kartę czasu pracy projektu

Można utworzyć i przesłać kartę czasu pracy projektu w aplikacji. Można także w nowej karcie czasu pracy opierać się na informacjach z poprzedniej karty czasu pracy, zapisanych wierszy lub przypisanych działaniach w projekcie. Jeśli wyznaczono Cię jako pełnomocnika, należy również wprowadzić kartę czasu pracy dla innego pracownika. Aby utworzyć kartę czasu pracy jako użytkownik delegowany, wybierz przycisk **Menu**, a następnie wybierz nazwę zasobu.

Strona karty czasu pracy spowoduje utworzenie nowej karty czasu pracy dla okresu karty czasu pracy, na podstawie bieżącej daty. Wyświetlany jest tydzień roboczy. Jeśli okres w karcie czasu pracy obejmuje wiele tygodni, można wybrać inny tydzień roboczy na kartach tygodnia pracy.
Jeśli istnieje karta czasu pracy dla bieżącej daty, zostanie wyświetlona. Aby utworzyć nową kartę czasu pracy w innym okresie karty czasu pracy, należy wybrać przycisk **Menu**, a następnie wybrać opcję **Nowa karta czasu pracy**.

Można wprowadzić informacje o projekcie, klikając akcję **Dodaj czas** lub **Kopiuj czas z**. Akcja **Kopiuj czas z** spowoduje skopiowanie informacji z wiersza projektu, ale nie godzin. Menu **Kopiuj czas z** zawiera następujące opcje:

- **Kopiuj z istniejącej karty czasu pracy** — kopiowanie wierszy karty czasu pracy z istniejącej karty czasu pracy.

- **Kopiuj z pozycji ulubionych** — umożliwia tworzenie nowych kart czasu pracy za pomocą ustawień wybranych jako ulubione.

- **Kopiuj z przypisania** — tworzy nowe wiersze karty czasu pracy z przypisanych projektów.

Wyświetlane informacje o projekcie zależą od parametrów mobilnych zdefiniowanych na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**.

W polu **Firma** wybierz firmę, dla której wykonywano prace projektowe. Uwaga: Pole **Firma** jest dostępne tylko wtedy, gdy włączono obsługę międzyfirmowej karty czasu pracy dla firmy.

Wybierz odbiorcę, który jest skojarzony z projektem w karcie czasu pracy. Dla wersji początkowej na Android, wprowadzanie według odbiorcy nie jest obsługiwane, ponieważ najpierw trzeba wybrać projekt. Jeśli najpierw wybierzesz opcję projekt, pole **odbiorcy** jest wypełniane automatycznie.

W polu **Projekt** wybierz projekt, dla którego jest określany czas. W polu **Odbiorca** jest wprowadzana automatycznie wartość.

Wyszukiwanie odbiorcy i projektu umożliwia wyszukiwanie między odbiorcami i projektami.

Wybierz odpowiednie informacje w polach **Kategoria**, **Działanie**, **Właściwość wiersza**, **Grupa podatków**, i **Grupa podatków dla pozycji**. Pola te mogą zostać zastąpione.

Pole **Właściwość wiersza** zostanie ustawione jako wartość domyślna na podstawie parametrów księgowania i zarządzania projektami. Po włączeniu parametrów kategorii/zasobów i projektów/kategorii wartość **właściwość wiersza** zostanie ustawiona jako wartość domyślna zdefiniowana dla tej weryfikacji. Jeśli parametry projektu/kategorii i kategorii/zasobów nie są włączone, wartość **właściwość wiersza** będzie domyślnie ustawiona zgodnie z polem **Grupa podatków dla pozycji** na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**. Wartość **właściwość wiersza** można zastąpić.

Wybierz dzień, aby dodać czas. Wprowadź liczby godzin przepracowanych każdego dnia.

Aby dodać komentarze dotyczące wprowadzanych godzin, kliknij **Dodaj komentarze**, a następnie wprowadź komentarze dla wewnętrznej grupy odbiorców, grupy odbiorców lub obu tych grup.
Komentarze wewnętrzne mogą przeglądać kierownicy projektów. Komentarze odbiorcy są uwzględnione na fakturach.

Aby zapisać wiersz jako ulubiony, zaznacz pole wyboru, a następnie kliknij przycisk **Zapisz w ulubionych**.

Aplikacja mobilna nie obsługuje wymiaru finansowego i załączników.

Kontynuuj dodawanie potrzebnych wierszy projektu, aby dokończyć tworzenie karty czasu pracy.

Kliknij przycisk **Prześlij**, aby wysłać kartę czasu pracy do zatwierdzenia przepływu pracy.

## <a name="review-timesheets"></a>Przeglądanie kart czasu pracy

Lista kart czasu pracy, które musiały zostać poddane kontroli, jest dostępna w menu. To opcja jest dostępna tylko jeśli wyznaczono Cię jako osobę zatwierdzającą przepływ pracy. Obsługiwane są zarówno zatwierdzanie nagłówka, jak i zatwierdzanie wierszy. Zatwierdzanie na poziomie wiersza umożliwia zaznaczenie jednego lub kilku wierszy do zatwierdzenia. Po przejrzeniu informacji karty czasu pracy, kliknij przycisk **Zatwierdź**, **Deleguj**, lub **Zwróć** aby kontynuować przepływ pracy.
