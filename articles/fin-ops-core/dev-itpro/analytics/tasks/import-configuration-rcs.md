---
title: (Raportowanie elektroniczne) Importowanie konfiguracji z RCS
description: Ten temat zawiera informacje o sposobach importowania przez użytkownika nowej wersji konfiguracji ER ze RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea2bfd2514be666d05165410ca27041a86464715
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143230"
---
# <a name="er-import-configurations-from-rcs"></a>(Raportowanie elektroniczne) Importowanie konfiguracji z RCS

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administratora systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji raportowania elektronicznego (ER) z usługi Microsoft Regulatory Configuration Services (RCS). W tym przykładzie zostanie wybrana wersja konfiguracji ER systemu, która została skonfigurowana w wystąpieniu klasy RCS i zaimportowana do bieżącego wystąpienia dla przykładowej firmy, Litware, Inc. Te kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są wspólne dla różnych firm. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze [Tworzenie dostawców konfiguracji i oznacz je jako aktywne](er-configuration-provider-mark-it-active-2016-11.md). Aby wykonać te kroki, trzeba również mieć dostęp do instancji klasy RCS zawierającej co najmniej jedną konfigurację ER albo w stanie **Wykonano**, albo **Udostępniono**.

1. Wybierz kolejno opcje **Administrowanie organizacją** > **Obszary robocze** > **Raportowanie elektroniczne**. 
2. Upewnij się, że dostawca konfiguracji dla przykładowej firmy Litware, Inc. jest dostępny i oznaczony jako **Aktywny** Jeśli ten dostawca konfiguracji nie jest widoczny, wykonaj kroki opisane w temacie [Utwórz dostawców konfiguracji i oznacz ich jako aktywnych](er-configuration-provider-mark-it-active-2016-11.md). 
3. Jeśli w firmie nie zainicjowano obsługi administracyjnej żadnego środowiska RCS, należy kliknąć łącze zewnętrzne **Regulatory services — Konfiguracja** i postępować zgodnie z instrukcjami w celu zapewnienia obsługi środowiska RCS. 
4. Kliknij **Parametry raportowania elektronicznego**. 
5. Kliknij kartę **RCS**. 
6. Jeśli dla firmy została już zainicjowana obsługa środowiska RCS, w celu uzyskania dostępu do tej strony należy skorzystać z przedstawionych w adresach URL stron. 
7. Zamknij stronę. 

## <a name="register-a-new-er-repository"></a>Rejestrowanie nowego repozytorium ER. 
1. Na liście oznacz wybrany wiersz. 
2. Zaznacz dostawcę Litware, Inc. 
3. Kliknij Repozytoria. 
4. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe. 
5. W polu Typ repozytorium konfiguracji wpisz „RCS”. 
6. Kliknij opcję Utwórz repozytorium. 
7. Wprowadź lub wybierz wartość w polu wyświetlania nazwy środowiska RCS. 
8. Wybierz żądany wartość usługi RCS. Zwróć uwagę, że możesz mieć kilka z nich. 
9. Kliknij przycisk OK. 

## <a name="import-er-configurations-from-rcs-based-repository"></a>Importowanie konfiguracji modułu Raportowanie elektroniczne z repozytorium opartym na RCS
1. Kliknij przycisk **Pokaż filtry.** 
2. Wprowadź wartość filtru „RCS” w polu **Nazwa typu**, używając operatora filtru **Zaczyna się na**. 
3. Po otwarciu wybranego repozytorium na stronie **Łączenie z usługami Regulatory Configuration Services**, kliknij przycisk **Kliknij tutaj, aby połączyć się z łączem usług Regulatory Configuration Services**. 
4. Kliknij przycisk **Otwórz.** 
5. Kliknij przycisk **Zamknij**. 
6. Wybierz żądaną wersję konfiguracji modułu ER i kliknij przycisk **Importuj**, aby przenieść ją do bieżącego wystąpienia.

