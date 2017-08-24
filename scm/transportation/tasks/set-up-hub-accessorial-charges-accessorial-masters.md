--- 
title: "Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych"
description: "W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum."
author: BibiSp
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 752a9a9a755ae7e4f2793fc712cc0c37c614ae71
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-hub-accessorial-charges-and-accessorial-masters"></a>Konfigurowanie opłat za usługi dodatkowe centrum i danych głównych usług dodatkowych

[!include[task guide banner](../../includes/task-guide-banner.md)]

W tej procedurze pokazano sposób tworzenia danych głównych usług dodatkowych dla centrum oraz użycia tych danych do utworzenie opłaty za usługi dodatkowe centrum. Procedura wykorzystuje zestaw danych firmy USMF. Konfiguracji zazwyczaj dokonuje koordynator transportu.


## <a name="set-up-a-hub-master"></a>Ustawianie głównego centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Główne usługi dodatkowe.
2. Kliknij przycisk Nowy.
3. W polu Główne dodatkowe usługi wpisz wartość.
4. W polu Nazwa wpisz wartość.
5. W polu Typ dodatkowych usług wybierz opcję „Centrum”.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="set-up-a-hub-accessorial-charge"></a>Konfigurowanie opłaty za usługi dodatkowe centrum
1. Wybierz kolejno opcje Zarządzanie transportem > Ustawienia > Ocena > Opłaty współpracownika centrum.
2. Kliknij przycisk Nowy.
3. W polu Identyfikator współpracownika centrum wpisz wartość.
4. W polu Centrum kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
5. Na liście znajdź i zaznacz odpowiedni rekord.
6. W polu Pozycja centrum wybierz opcję.
    * Opłatę można utworzyć za odbiór lub dostawę. W zależności od wybranej opcji opłata będzie stosowana do odpowiedniego segmentu transportu na trasie.  
7. W polu Główne dodatkowe usługi kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
8. Na liście kliknij łącze w wybranym wierszu.
    * Wybierz utworzone właśnie dane główne.  
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.


