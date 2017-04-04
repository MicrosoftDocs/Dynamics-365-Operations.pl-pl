---
title: "Zapasów dostępnych mobilnych obszaru roboczego Microsoft Dynamics 365 dla operacji aplikacji"
description: "Obszar roboczy mobilnych dostępnych zapasów pozwala uzyskać mobilnych wgląd w informacje zastrzeżone i dostępnych zapasów, zawsze i wszędzie."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267094
ms.assetid: 85058f55-e566-40e2-9234-42d3e4fe5ff6
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 2ad48765528e1d1c6e7c90417b54a248ec79f546
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-on-hand-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Zapasów dostępnych mobilnych obszaru roboczego Microsoft Dynamics 365 dla operacji aplikacji

Obszar roboczy mobilnych dostępnych zapasów pozwala uzyskać mobilnych wgląd w informacje zastrzeżone i dostępnych zapasów, zawsze i wszędzie. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                        |
|----------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat usługi Microsoft Dynamics 365 dla operacji platformy mobilnej | [Dynamics 365 dla operacji platformy mobilnej](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                   |
| Dynamics 365 dla operacji                                          | Środowisku Microsoft Dynamics 365 dla wersji operacji 1611 i Microsoft Dynamics dla operacji platformy aktualizacji 3 (listopad 2016) |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, aby włączyć obszary robocze, które znajdują się w sieci Microsoft Dynamics 365 dla operacji.                                       |
| Przenośne urządzenie, które ma 365 Dynamics dla operacji zainstalowaną aplikację | Pobierz 365 Dynamics dla operacji aplikacji ze sklepu internetowego.                                                                           |

## <a name="introduction"></a>Wprowadzenie
Zazwyczaj firmy mają wiele wydaniami i przyjęciami wielu zapasów każdego dnia. Przesunięcia te stale zmianę stanu dostępnych zapasów. Obszar roboczy mobilnych dostępnych zapasów pozwala sprawdzić stan międzyfirmowej dostępnych zapasów, tak, aby można było uzyskać najnowsze informacje do magazynu danych na urządzeniu przenośnym, wybranych przez użytkownika. Niezależnie od tego, czy pracujesz w magazynie, zakupów, sprzedaży, produkcji lub zarządzania, lub mieć inne role można dostęp do danych dostępnych zapasów, zawsze i wszędzie. Mobilne obszar roboczy zapewnia natychmiastowy przegląd stanu dostępnych zapasów w udogodnienia i umożliwia wyświetlanie dostępnych zapasów na udogodnienia, bieżących rezerwacji materiału i bezwarunkowe dostępnych zapasów. Można również wprowadzić numery zapasów do kwerendy dostępnych zapasów i wykonywać filtrowane wyszukiwanie dostępnych produktów lub wariantów. W szczególności przenośnych obszar roboczy oferuje następujące funkcje:

-   Możesz określić numer produktu lub nazwa produktu znaleźć produkty można wyświetlić stan dostępnych zapasów.
-   Dla wybranych produktów można wyświetlić następujące informacje:
    -   Dostępne zapasy dla każdej witryny
    -   Dostępnych zapasów na magazyn
    -   Dostępne zapasy według lokalizacji
    -   Dostępne zapasy na partię (dla kontrolowanych partii produktów)
    -   Dostępne zapasy na stan zapasów

<!-- -->

-   Produkt dostępnych zapasów jest pokazywana w następujący sposób:
    -   Przez Magazyn fizyczny (w tym widoku odpowiada całkowitej kwocie).
    -   Przez fizyczne zarezerwowane (Widok przedstawia kwoty zarezerwowane).
    -   Przez fizyczne dostępne (ten widok reprezentuje dostępna kwota, która nie ma żadnych zastrzeżeń.)

## <a name="get-started"></a>Rozpocznij
Aby rozpocząć pracę na urządzeniu przenośnym:

1.  Ze sklepu internetowego Pobierz i zainstaluj usługi Microsoft Dynamics 365 dla operacji aplikacji.
2.  Uruchom aplikację na urządzeniu.
3.  Podaj adres URL Dynamics 365.
4.  Wprowadzić firmę do logowania się. Na przykład wpisz **USMF**.
5.  Podczas pierwszego logowania, zostanie wyświetlony monit o nazwę użytkownika i hasło dla sieci Microsoft Dynamics 365 dla konta operacji. Wprowadź swoje poświadczenia. Po zalogowaniu się, można wyświetlić dostępne obszary robocze firmy.

Aby wyświetlić obszary robocze w aplikacji mobilnej, należy najpierw opublikować żądane obszary robocze do 365 Dynamics dla operacji aplikacji.

1.  Uruchom system Dynamics 365 dla operacji.
2.  Przejdź do **Administracja systemu**&gt;**instalacji**&gt;**parametrów systemu**.
3.  Wybierz **Opcje aplikacji mobilnych**.
4.  Wybierz obszar roboczy, aby opublikować mobilnej platformie.
5.  Wybierz **obszaru roboczego opublikować**.
6.  Odśwież swoje urządzenie, aby sprawdzić opublikowanych obszarów roboczych.

## <a name="view-the-onhand-inventory-for-a-product"></a>Wyświetl stan zapasów magazynowych dla produktu
1.  Na urządzeniu przenośnym, wybierz **dostępnych zapasów** obszaru roboczego.
2.  Wybierz **Sprawdź dostępne zapasy dla elementu**. Zobacz listę produktów, które są ładowane do aplikacji w trybie offline. Domyślnie elementy 50 są załadowane, ale można zmienić ten numer. Aby uzyskać więcej informacji zobacz Podręcznik wstępnie odczytu.
3.  Jeśli przedmiot nie ma na liście, wybierz opcję **Wyszukaj więcej** do online wyszukiwania w usłudze Dynamics 365 dla operacji. Wyszukaj według numeru produktu, lub przełącz się do wyszukiwania według nazwy produktu.
4.  Wybierz produkt. Jeśli element ma obrazu, obraz jest wyświetlany.
5.  Wybierz jedną z poniższych opcji, aby wyświetlić stan dostępnych zapasów:
    -   Przeglądaj dostępne zapasy dla każdej witryny
    -   Wyświetlanie dostępnych zapasów na magazyn
    -   Wyświetl dostępne zapasy według lokalizacji
    -   Przeglądaj dostępne zapasy na partię (dla kontrolowanych partii produktów)
    -   Wyświetl dostępne zapasy według stanu zapasów

    Produkt dostępnych zapasów jest pokazywana w następujący sposób:
    -   Przez Magazyn fizyczny (w tym widoku odpowiada całkowitej kwocie).
    -   Przez fizyczne zarezerwowane (Widok przedstawia kwoty zarezerwowane).
    -   Przez fizyczne dostępne (w tym widoku reprezentuje dostępna kwota, która nie ma żadnych zastrzeżeń).




