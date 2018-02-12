---
title: Rozszerzanie funkcji programu Microsoft Dynamics 365 for Talent
description: "Po utworzeniu dowolnej aplikacji w środowisku Microsoft PowerApps można uruchomić takie aplikacje za pomocą łączy w programie Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-28
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cfd3b475b113fdab4ceeb3e636fea6c9134ab982
ms.openlocfilehash: 0ab829803634871c9060daa381bd02d7d2bbdf42
ms.contentlocale: pl-pl
ms.lasthandoff: 12/01/2017

---
# <a name="extend-the-functionality-of-microsoft-dynamics-365-for-talent"></a>Rozszerzanie funkcji programu Microsoft Dynamics 365 for Talent
Po utworzeniu dowolnej aplikacji w środowisku Microsoft PowerApps można uruchomić takie aplikacje za pomocą łączy w programie Microsoft Dynamics 365 for Talent. Aby skonfigurować dostęp do aplikacji, należy ustawić niektóre informacje w aplikacji Talent na stronie konfiguracji, którą można otworzyć z poziomu obszaru roboczego **Administrowanie systemem**.

## <a name="configuring-embedded-powerapps-within-talent"></a>Konfiguracja osadzonych usług PowerApps w środowisku Talent
Na stronie **Ustaw osadzone usługi Microsoft PowerApps** można skonfigurować strony środowiska Talent do uruchamiania aplikacji PowerApps. Aby otworzyć stronę **Ustaw osadzone usługi Microsoft PowerApps**, otwórz obszar roboczy **Administrowanie systemem**, a następnie otwórz kartę **Łącza**. Wybierz opcję **Microsoft PowerApps** z grupy **Ustawienia**. 

Na tej stronie można wprowadzić lub ustawić następujące informacje: 

> - Nazwa opisowa lub identyfikator dla każdej aplikacji PowerApps.
> - Niepowtarzalny identyfikator (GUID) dla każdej aplikacji dodawanej do strony Talent. Identyfikator aplikacji jest dostępny w witrynie usługi PowerApps [powerapps.com](http://powerapps.com/). 
> - Strona, z której użytkownicy mogą otworzyć aplikację lub raport. Nie wszystkie strony środowiska Talent obsługują osadzone aplikacje PowerApps i raporty Power BI. 

 > [!NOTE]
 >  Należy wprowadzić nazwę wewnętrzną strony, a nie nazwę wyświetlaną u góry strony. Aby znaleźć nazwę wewnętrzną, otwórz stronę, której nazwy szukasz, i kliknij w dowolnym miejscu na stronie. Po otwarciu menu, umieść kursor myszy nad pozycją **Informacje o formularzu**. Wewnętrzna nazwa formularza zostanie wyświetlona obok pozycji **Informacje o formularzu** w menu.
 
> - Określ formant formularza, z którego aplikacja może pobrać dane kontekstowe. Aplikacja może na przykład używać danych na temat pracownika. W przypadku wprowadzenia strony **Pracownik** w polu **Kontekst** przy uruchamianiu aplikacji będzie otwierana strona **Pracownik**. Wpis w **polu Kontekst** jest opcjonalny. 
> - Ustaw rozmiar okna dialogowego, w którym będzie uruchamiana aplikacja PowerApps. Okna dialogowe są oznaczone jako „małe” lub „duże”, co umożliwia optymalizację interfejsu użytkownika, gdy aplikacja jest otwierana odpowiednio na telefonie lub większym urządzeniu. 

Można również określić firmy, dla których aplikacja będzie dostępne, lub udostępnić ją dla wszystkich firm. Domyślnie aplikacje PowerApps są dostępne dla wszystkich firm.

## <a name="opening-an-application"></a>Otwieranie aplikacji
Po skonfigurowaniu osadzonych aplikacji PowerApps łącza do określonych aplikacji zostaną dodane do stron w środowisku Talent. Aby otworzyć aplikację, kliknij łącze. 



