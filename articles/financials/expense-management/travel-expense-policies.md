---
title: Definiowanie zasad dotyczących wydatków
description: Można zdefiniować zasady dotyczące wydatków, których pracownicy muszą przestrzegać przy wprowadzaniu i wysyłaniu raportów z wydatków i wniosków wyjazdowych w rozwiązaniu Microsoft Dynamics 365 for Finance and Operations.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f0ff56f0ff106bc168b6a27612e08743a539a07
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/07/2019
ms.locfileid: "1514446"
---
# <a name="expense-policies"></a>Zasady dotyczące wydatków

[!include [banner](../includes/banner.md)]

Można zdefiniować zasady, których pracownicy muszą przestrzegać podczas wprowadzania i przesyłania raportów z wydatków i wniosków wyjazdowych.         
Wdrożenie zasad dotyczących wydatków może się przyczynić do efektywniejszego zarządzania wydatkami.         

Można na przykład określić zasadę dotyczącą wydatków na zakwaterowanie w Nowym Jorku, która stanowi, że wydatki nie mogą przekroczyć 250 zł za noc.       
Jeśli pracownik prześle raport z wydatków lub wniosek wyjazdowy, w którym ta kwota będzie przekroczona, system powiadomi pracownika,        
że została przekroczona kwota wydatków określona w zasadach. Podczas definiowania zasady można skonfigurować wiadomość,        
jaką otrzyma pracownik.      
        
Można zdefiniować trzy typy zasad:         
        
- Ostrzeżenie — umożliwia pracownikowi przesłanie raportu z wydatków lub wniosku wyjazdowego, ale wydatek zostanie oznaczony dla wszystkich osób zatwierdzających i        
  do późniejszego raportowania.        

- Błąd — wymaga, aby pracownik zmienił wydatek na zgodny z zasadami przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.       
 
 - Uzasadnienie — wymaga, aby pracownik lub menedżer wprowadził uzasadnienie przekroczenia kwoty w zasadach przed przesłaniem raportu z wydatków lub wniosku wyjazdowego.        

# <a name="policy-tips"></a>Porady dotyczące zasad
Oto kilka sugestii ułatwiających tworzenie nowych zasad zarządzania wydatkami. 
* Zasady obowiązują od dnia ich wprowadzenia; nie zaczną obowiązywać, jeśli zasada zostanie utworzona z datą późniejszą niż data wystąpienia wydatku. Jeśli na przykład nowe zasady są tworzone dzisiaj w celu wymuszenia maksymalnego kosztu posiłku wynoszącego $50, wówczas wszelkie istniejące wydatki wprowadzone z datą wczorajszą nie będą sprawdzane w odniesieniu do tej zasady.
* Podczas tworzenia zasady dla kategorii wydatków, która może być wyszczególniona, należy rozważyć dodanie warunku dla typu wiersza wydatku. Niektóre zasady, takie jak wymaganie przyjęcia paragonu, mogą nie mieć sensu w przypadku wierszy wyszczególnionych i powinny być stosowane tylko do wierszy nagłówka lub wierszy bez pozycji. 

# <a name="when-to-evaluate-policies"></a>Kiedy oceniać zasady

W parametrach zarządzania wydatkami istnieje możliwość oceny zasad zarządzania wydatkami podczas zapisywania wiersza lub przesyłania raportu z wydatków. Jeśli zostanie wybrana opcja oceny, kiedy wiersz zostanie zapisany, użytkownicy będą wcześniej wiedzieli, co muszą zrobić, aby od razu wypełnić cały raporty z wydatków. W przeciwnym wypadku można opóźnić ocenianie zasad i zaoszczędzić czas, jeśli podczas przesyłania do przepływu pracy następuje weryfikacja.
