---
title: Rozumienie pól Data i Godzina
description: Opis oczekiwań podczas używania pól daty i godziny w rozwiązaniu Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d843eb8cefcd0f2f45c8956cd451f88ca6336efb
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130454"
---
# <a name="understand-date-and-time-fields"></a>Opis pól Data i Godzina

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

**Pola daty i godziny** stanowią podstawową koncepcję w Dynamics 365 Human Resources. Ważne jest, aby zrozumieć sposób pracy z danymi **Daty i godziny** w formularzach Dataverse i źródłach zewnętrznych.

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a>Opis różnicy między typami danych pól daty oraz daty i godziny

Pola **Data i godzina** zawierają informacje o strefie czasowej, natomiast pola **Data** nie. Pola **Data** zawierają te same informacje w dowolnej lokalizacji. Wprowadzenie daty w polu **Data** powoduje, że Human Resources zapisuje tę samą datę do bazy danych.

W przypadku wyświetlania danych w polu **Data i Godzina** Human Resources dostosowuje datę i godzinę na podstawie konfiguracji strefy czasowej użytkownika w formularzu **Opcje użytkownika** (**Wspólne > Ustawienia > Opcje użytkownika**). Data i godzina wprowadzona w polu mogą być inne niż informacje zapisane w bazie danych.

[![Formularz Opcje użytkownika](./media/useroptionsform.png)](./media/useroptionsform.png)

## <a name="understanding-date-and-time-fields-in-forms"></a>Rozumienie użycia pól Data i Godzina w formularzach 

W polu **Data i Godzina**, dane wyświetlane na ekranie nie są takie same jak dane przechowywane w bazie danych, jeśli strefa czasowa użytkownika nie jest ustawiona na Uniwersalny czas koordynowany (UTC). Dane w polach **Data i godzina** są zawsze zapisywane jako czas UTC.

[![Formularz pracownika UTC](./media/worker-form.png)](./media/worker-form.png)

## <a name="understand-date-and-time-fields-in-the-database"></a>Rozumienie użycia pól Data i Godzina w bazie danych 

Gdy Human Resources zapisuje wartość **Data i godzina** w bazie danych, zapisuje dane w formacie UTC. Umożliwia to użytkownikom wyświetlanie wszelkich danych dotyczących **Data i godzina** w odniesieniu do stref czasowych zdefiniowanych w opcjach użytkownika.
 
W powyższym przykładzie czas rozpoczęcia to punkt w czasie, a nie określona data. Zmiana strefy czasowej zalogowanego użytkownika z poziomu GMT +12:00 na GMT UTC powoduje, że ten sam rekord pokazuje dane w formacie 04/30/2019 12:00:00 zamiast 05/01/2019 12:00:00.
  
W poniższym przykładzie zatrudnienie pracownika nr. 000724 staje się aktywne w tym samym czasie, niezależnie od strefy czasowej. Pracownik będzie aktywny w dniu 04/30/2019 w strefie czasowej GMT, który jest taki sam jak 05/01/2019 w strefie GMT +12:00. Odnoszą się do tego samego punktu w czasie, a nie do określonej daty. 

[![Formularz pracownika GMT](./media/worker-form2.png)](./media/worker-form2.png)

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a>Dane daty i godziny w strukturze zarządzania danymi, Excel, Dataverse i Power BI 

Środowisko zarządzania danymi, dodatek programu Excel, Dataverse i raportowanie Power BI są przeznaczone do interakcji z danymi bezpośrednio na poziomie bazy danych. Ponieważ nie istnieje klient, który dostosowuje dane **Data i godzina** do strefy czasowej użytkownika, wszystkie wartości **Data i godzina** są w formacie UTC, co może prowadzić do niektórych nieprawidłowych założeń podczas wprowadzania lub wyświetlania danych.  
 
Dane **Data i godzina** przesłane za pośrednictwem DMF, programu Excel lub Dataverse są uznawane przez bazę danych w formacie UTC. Może to spowodować pomyłkę w przypadku, gdy przesłana wartość **Data i godzina** nie zostanie wyświetlona w oczekiwany sposób, ponieważ użytkownik wyświetlający dane nie ma ustawionej czasu UTC dla danej strefy czasowej użytkownika. 
 
Podczas eksportowania danych ten sam element może mieć stan odwrotny. Dane **Data i godzina** w wyeksportowanej jednostce DMF mogą być różne w zależności od tego, co jest wyświetlane w kliencie systemu Dynamics. 
 
W przypadku używania źródeł zewnętrznych, takich jak DMF do wyświetlania lub tworzenia danych, należy pamiętać, że wartości **Data i godzina** są uwzględniane domyślnie w formacie UTC, niezależnie od strefy czasowej komputera użytkownika lub jego bieżących ustawień strefy czasowej użytkownika. 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a>Przykłady tego samego rekordu wyświetlanego w różnych obszarach produktów 

**Human Resources ze strefą czasową użytkownika ustawioną jako UTC**

[![Formularz pracownika ustawiony na czas UTC](./media/worker-form3.png)](./media/worker-form3.png)

**Human Resources ze strefą czasową użytkownika ustawioną jako GMT +12:00** 

[![Formularz pracownika ustawiony na czas GMT](./media/worker-form4.png)](./media/worker-form4.png)

**Excel za pośrednictwem protokołu OData**

[![Excel za pośrednictwem protokołu OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)

**Ustawianie DMF**

[![Ustawianie DMF](./media/DMFStaging.png)](./media/DMFStaging.png)

**Eksportowanie DMF**

[![Eksportowanie DMF](./media/DMFexport.png)](./media/DMFexport.png)

**Excel za pośrednictwem Dataverse**

[![Excel za pośrednictwem Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)

## <a name="see-also"></a>Informacje dodatkowe

[Dane daty i godziny](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[Preferowana strefa czasowa użytkownika](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
