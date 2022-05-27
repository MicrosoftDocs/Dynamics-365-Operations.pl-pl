---
title: Tworzenie łączy z rozwiązania Human Resources do innego środowiska
description: W tym temacie opisano sposób tworzenia łącza z rozwiązania Microsoft Dynamics 365 Human Resources do innego środowiska rozwiązania Dynamics 365.
author: twheeloc
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-29-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d20eef4b4861d85ead1d47ca493c3a5c2d2d85e8
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712631"
---
# <a name="create-links-from-human-resources-to-another-finance-environment"></a>Tworzenie łączy z rozwiązania Human Resources do innego środowiska Finance

Klient może mieć dwa środowiska systemu Dynamics 365, w których pracuje. Na przykład klient może mieć środowisko Dynamics 365 Human Resources w infrastrukturze finansowej i musi połączyć się z innym środowiskiem Dynamics 365 Finance. 

Ta funkcja zezwala na łącza ze strony Human Resources do określonej strony w innym środowisku Finance. Podczas konfigurowania łączy można określić miejsce jego otwarcia w Human Resources oraz stronę docelową, która zostanie otwarta w innym środowisku.

> [!Note] 
> Aby korzystać z tej funkcji, musisz włączyć **Ulepszenia w zakresie obsługi zasobów ludzkich** w **Zarządzaniu funkcjami** .

## <a name="configure-target-systems"></a>Konfigurowanie systemów docelowych

W systemie Zasoby ludzkie administratorzy systemu mogą definiować łącza, które będą się pojawić na stronach **Human Resources**. Częścią konfiguracji jest środowisko aplikacji Finance, do którego chcesz przejść jako do „lokalizacji docelowej” łącza. 

Aby skonfigurować system docelowy:
1. Na stronie **Konfiguruj łącza** wybierz pozycję **Konfiguruj system docelowy**.  
2. Wprowadź nazwę systemu docelowego i podaj adres URL środowiska Finance. Po skonfigurowaniu systemów docelowych można zdefiniować łącza.

## <a name="configure-links"></a>Konfiguruj łącza

Każde tworzone łącze będzie miało zdefiniowane następujące informacje:
 - **Łącze**: Nazwa łącza skrótu. Używane tylko do identyfikacji.
 - **Włącz to łącze**: ustaw wartość **Tak**, jeśli łącze ma być wyświetlane użytkownikom aplikacji Human Resources.
 - **Nazwa wyświetlana**: Wprowadź nazwę, która pojawi się jako łącze do środowiska dodatkowego. 
 - **Pokaż łącze na wierzchu w formularzu**: wybierz stronę, na której łącze ma być wyświetlane. Łącza mogą być dostępne tylko w **obszarze roboczym Samoobsługa pracownika etatowego** oraz na stronach **Praca**, **Stanowisko**, **Pracownik** i **Uproszczony** pracownik.
 - **Grupa**: Łącza można zorganizować przy użyciu grup. Wybierz istniejącą grupę lub utwórz nową, korzystając z kolumny **Grupa**.
 - **System docelowy**: wybierz docelowy system, który został utworzony za pomocą opcji **Konfiguruj system docelowy**. Będzie to drugorzędne środowisko, które będzie używane podczas nawigowania za pomocą łącza.
 - **Użyj bieżącej firmy użytkownika**: wybierz wartość **Tak**, aby użyć bieżącej firmy użytkownika podczas przechodzenia do Finance. Wybierz wartość **Nie**, to można wybrać firmę, która ma być używana.
 - **Element menu docelowego**: Wprowadź element menu ze środowiska Finance, którego łącze powinno używać podczas nawigacji. Dostępne są elementy menu, do których można przechodzić bezpośrednio. 

   Aby znaleźć wymagany element menu:
   1. Przejdź do środowiska Finance i otwórz stronę będącą celem nawigacji. 
   2. Skopiuj element menu z adresu URL. Na przykład jeśli chcesz, aby łącze prowadziło do listy pracowników etatowych w aplikacji Finance and Operations, wprowadź wartość widoczną po elemencie „&mi” w adresie URL. 
   3. Elementem menu powodującym przejście do strony z listą pracowników w tym przykładzie jest HcmWorkerListPage_Employees.

 - **Łącze do źródła danych**: wybierz źródło danych, do którego odwołuje się łącze. Dostępne są najczęściej używane źródła, takie jak **Pracownik** i **Stanowisko**.

### <a name="access-to-links"></a>Dostęp do łączy

Administratorzy systemu będą widzieć nowo utworzone łącza na wskazanych stronach nawet wtedy, gdy opcja **Włącz to łącze** jest ustawiona na **Nie**. Ten mechanizm może służyć do testowania łączy przed ich udostępnieniem innym pracownikom. Posiadacze wszystkich pozostałych ról będą widzieć skonfigurowane łącza tylko wtedy, gdy opcja **Włącz to łącze** jest ustawiona na **Tak**. Pracownicy mający dostęp do stron, w których łącza są wyświetlane, będą mogli używać tych łączy.

Użytkownicy muszą mieć również uprawnienia zabezpieczeń w środowisku pomocniczym, które mają dostęp do stron w tym środowisku. Jeśli tak nie jest, po kliknięciu łącza pojawi się okno dialogowe mówiące o zabezpieczeniach.

