---
title: "Obszar mobilnych zamówień sprzedaży dla Microsoft Dynamics 365 dla operacji aplikacji"
description: "Z obszaru roboczego mobilnych zamówień sprzedaży, możesz na bieżąco w zamówieniach sprzedaży w dowolnym miejscu i o dowolnej porze."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: dbc6dc39-b535-42d3-9fbd-4724597388ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 7a0a2af2094e3e5be757d3dd82255769677b96ea
ms.openlocfilehash: 851c53e1c53fb37488ed86e25e3ede83ca0541db
ms.lasthandoff: 03/31/2017


---

# <a name="sales-orders-mobile-workspace-for-microsoft-dynamics-365-for-operations-app"></a>Obszar mobilnych zamówień sprzedaży dla Microsoft Dynamics 365 dla operacji aplikacji

Z obszaru roboczego mobilnych zamówień sprzedaży, możesz na bieżąco w zamówieniach sprzedaży w dowolnym miejscu i o dowolnej porze. 

<a name="prerequisites"></a>Wymagania wstępne
-------------

| Wymaganie wstępne                                                         | opis                                                                                                                                                                   |
|----------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Przeczytaj na temat usługi Microsoft Dynamics 365 dla operacji platformy mobilnej | [Dynamics 365 dla operacji platformy mobilnej](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform)                                                              |
| Dynamics 365 dla operacji                                          | Upewnij się, że używasz środowisku Microsoft Dynamics 365 dla wersji operacji 1611 i Microsoft Dynamics dla platform operacji aktualizacji 3 (listopad 2016). |
| Poprawka KB 3215650                                                    | Zainstaluj poprawkę, aby włączyć obszary robocze, które znajdują się w usłudze Microsoft Dynamics 365 dla operacji.                                                                       |
| Przenośne urządzenie, które ma 365 Dynamics dla operacji zainstalowaną aplikację | Pobierz 365 Dynamics dla operacji aplikacji ze sklepu internetowego.                                                                                                      |

## <a name="overview"></a>Przegląd
Ten obszar roboczy mobilnych uzyskuje dostęp do 365 Dynamics dla operacji aplikacji i pozwala wyświetlić szczegółowe informacje dotyczące każdego zamówienia sprzedaży, takie jak stan zlecenia, klienta, informacje kontaktowe i informacje kontaktowe przyjmujący zamówienia. Mobilne obszar roboczy zapewnia natychmiastowy przegląd zamówień sprzedaży. Można wyświetlić zamówienia sprzedaży przez nabywcę, lub przeglądanie wszystkich zamówień sprzedaży lub wyświetlanie informacji na temat określonego zamówienia sprzedaży. Mobilne obszar roboczy zawiera dwa widoki, aby pomóc w analizie zamówień sprzedaży w głębi.

### <a name="view-all-sales-orders"></a>Przeglądanie wszystkich zamówień sprzedaży

Ten widok wyświetla listę wszystkich zamówień sprzedaży.

-   Użyj jednego z następujących filtrów, aby wybrać zamówień sprzedaży, które chcesz wyświetlić.
    -   Wyszukaj według zamówienia sprzedaży
    -   Szukaj według konta odbiorcy
    -   Wyszukiwanie według nazwy odbiorcy
    -   Wyszukaj według stanu
    -   Wyszukaj według statusu wydania
    -   Wyszukaj według Data i godzina utworzenia

<!-- -->

-   Po wybraniu zamówienia sprzedaży można wyświetlić szczegółowe informacje o określonych zamówień. W szczególności można wyświetlać:
    -   Informacje o nazwę i adres odbiorcy
    -   Daty inne zamówienie sprzedaży, takie jak żądana data wysyłki i potwierdzona data wysyłki
    -   Informacje kontaktowe przyjmujący zamówienia
    -   Informacje kontaktowe klienta
    -   Wiersze zamówienia
    -   Przesyłki, które pokazują, jak i kiedy zamówienie sprzedaży zostało wysłane

### <a name="view-orders-for-a-customer-"></a>Umożliwia wyświetlanie zamówień dla odbiorcy ** **

Ten widok wyświetla listę zamówień sprzedaży dla nabywcy.

-   Użyj jednej z następujących filtrów do wyświetlania zamówień dla odbiorcy.
    -   Wyszukiwanie według nazwy
    -   Szukaj według konta

<!-- -->

-   Po wybraniu odbiorcy, można przeglądać:
    -   Nazwa odbiorcy i grupy
    -   Informacje kontaktowe klienta
    -   Zamówienia sprzedaży i szczegółowe informacje dotyczące zamówień sprzedaży:
        -   Informacje o nazwę i adres odbiorcy
        -   Dat innego zamówienia sprzedaży
        -   Informacje kontaktowe przyjmujący zamówienia
        -   Informacje kontaktowe klienta
        -   Wiersze zamówienia
        -   Przesyłki, które pokazują, jak i kiedy zostały wydane zamówienia sprzedaży

## <a name="get-started"></a>Rozpocznij
Wykonaj poniższe czynności, aby rozpocząć pracę z obszarem roboczym mobilnych zamówień sprzedaży na urządzeniu przenośnym.

1.  Na sklepu internetowego Pobierz i zainstaluj usługi Microsoft Dynamics 365 dla operacji aplikacji.
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

## <a name="view-information-about-sales-orders-for-a-customer"></a>Wyświetlanie informacji o zamówieniach sprzedaży dla nabywcy
1.  Na urządzeniu przenośnym, wybierz **zamówienia sprzedaży** obszaru roboczego.
2.  Wybierz **zamówienia dla klienta zobacz**.
3.  Użyj ** konta ** lub ** nazwa odbiorcy ** informacje w celu znalezienia żądanego klienta.
4.  Wybierz odbiorcę.
5.  Wybierz **informacji o kontakcie** lub **zamówienia sprzedaży**.
6.  Jeśli **zamówienia sprzedaży** jest zaznaczona, zamówień sprzedaży dla klienta zostanie wyświetlona lista.
7.  Wybierz **zamówienie sprzedaży**.
8.  W tym miejscu można wyświetlić informacje dotyczące wierszy zamówienia sprzedaży, przesyłek, informacji kontaktowych klientów i informacje kontaktowe przyjmujący zamówienia.




