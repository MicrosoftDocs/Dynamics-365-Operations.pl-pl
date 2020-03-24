---
title: Usuwanie wystąpienie
description: Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a40b9619e92b81272208ad4241a2455330a342a7
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124435"
---
# <a name="remove-an-instance"></a>Usuwanie wystąpienie

Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.

## <a name="remove-a-test-drive-environment"></a>Usuń środowisko testowe

Środowiska testowe aplikacji Human Resources mają ustawioną zasadę wygasania po 60 dniach. Jednak właściciele środowisk testowych mają możliwość wcześniejszego zakończenia okresu próbnego, wykonując następujące kroki. 

1. Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).
2. Wybierz opcję **Środowiska**.
3. Wybierz środowisko testowe, które ma nazwę o wzorcu podobnym do następującego: TestDrive -alias@domain
4. Wybierz opcję **Usuń** i potwierdź decyzję. 

Istniejące środowisko testowe zostanie usunięte. Po usunięciu środowiska możesz się zapisać na nowe środowisko testowe. 

## <a name="remove-a-production-environment"></a>Usuń środowisko produkcyjne

Temat ten opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Human Resources u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). 

Ponieważ środowisko aplikacji Human Resources jest „zawarte” w jednym środowisku usługi Power Apps, dostępne są dwie opcje do rozważenia. Pierwsza opcja polega na usunięciu całego środowiska usługi Power Apps, a druga na usunięciu tylko modułu Human Resources. Pierwsza opcja jest preferowana, jeżeli środowisko usługi Power Apps utworzono specjalnie do obsługi aplikacji Human Resources i dopiero rozpoczęto wdrażanie lub nie ma żadnych wiążących integracji. Drugą opcję należy zastosować, jeśli istnieje ustabilizowane środowisko usługi Power Apps wypełnione sformatowanymi danymi wykorzystywanymi w usługach Power Apps i Power Automate.

> [!Important]
> Przed usunięciem środowiska usługi Power Apps upewnij się, że nie jest ono używane do integrowania sformatowanych danych poza zakresem Human Resources. Należy również zwrócić uwagę, że nie można usuwać domyślnych środowisk usługi Power Apps. 

Aby usunąć całe środowisko usługi Power Apps, w tym aplikację Human Resources oraz powiązane aplikacje i przepływy:

1. Przejdź do [Centrum administracyjnego usługi Power Apps](https://admin.businessplatform.microsoft.com/).
2. Wybierz opcję **Środowiska**.
3. Zaznacz środowisko, które chcesz usunąć.
4. Wybierz opcję **Usuń** i potwierdź decyzję. 
5. Poczekaj na zakończenie usuwania.
6. Zaloguj się w usłudze [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) za pomocą konta użytego do zasubskrybowania aplikacji Human Resources. 
7. Wybierz projekt z aplikacją Human Resources, który zawiera środowisko. 
8. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**. 
9. Wybierz wystąpienie do usunięcia. 
10. Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.  

Aby usunąć środowisko Human Resources z istniejącego środowiska usługi Power Apps, wykonaj następujące kroki. Należy zauważyć, że konieczność zaangażowania działu pomocy technicznej i skontaktowania się z zespołem DevOps aplikacji Human Resources są tymczasowe, do czasu włączenia tej funkcji bezpośrednio w usłudze LCS.

1. Skontaktuj się z działem pomocy technicznej i zainicjuj wniosek o usunięcie.
2. Dział pomocy technicznej zainicjuje wniosek o usunięcie razem z zespołem DevOps aplikacji Human Resources. 
3. Po otrzymaniu informacji, że środowisko zostało usunięte, kontynuuj procedurę.
4.  Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Human Resources. 
5. Wybierz projekt z aplikacją Human Resources, który zawiera środowisko. 
6. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**. 
7. Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Niepowodzenie**.
8. Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję. 
