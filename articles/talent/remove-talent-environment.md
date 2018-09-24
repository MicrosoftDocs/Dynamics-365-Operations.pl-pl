---
title: "Usuwanie środowisk rozwiązania Talent"
description: "Ten temat przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 for Talent."
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
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
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 5080f1ec182b8cbdf281967185a1afeb9887f682
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="remove-talent-environments"></a>Usuwanie środowisk rozwiązania Talent

[!include [banner](includes/banner.md)]

Ten temat przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 for Talent.

## <a name="removing-a-test-drive-environment"></a>Usuwanie środowiska testowego

Środowiska testowe aplikacji Talent mają ustawioną zasadę wygasania po 60 dniach. Jednak właściciele środowisk testowych mają możliwość wcześniejszego zakończenia okresu próbnego, wykonując następujące kroki. 

1. Przejdź do [centrum administracyjnego usługi PowerApps](https://admin.businessplatform.microsoft.com/).
2. Wybierz opcję **Środowiska**.
3. Wybierz środowisko testowe, które ma nazwę o wzorcu podobnym do następującego: TestDrive -alias@domain
4. Wybierz opcję **Usuń** i potwierdź decyzję. 

Istniejące środowisko testowe zostanie usunięte. Po usunięciu środowiska możesz się zapisać na nowe środowisko testowe. 

## <a name="removing-a-production-environment"></a>Usuwanie środowiska produkcyjnego

Temat te opiera się na założeniu, że użytkownik dokonał zakupu aplikacji Talent u dostawcy rozwiązań chmurowych (CSP) lub w ramach umowy na architekturę przedsiębiorstwa (EA). 

Ponieważ środowisko aplikacji Talent jest „zawarte” w jednym środowisku usługi PowerApps, dostępne są dwie opcje do rozważenia. Pierwsza opcja polega na usunięciu całego środowiska usługi PowerApps, a druga na usunięciu tylko modułu Talent. Pierwsza opcja jest preferowana, jeżeli środowisko usługi PowerApps utworzono specjalnie do obsługi aplikacji Talent i dopiero rozpoczęto wdrażanie lub nie ma żadnych wiążących integracji. Drugą opcję należy zastosować, jeśli istnieje ustabilizowane środowisko usługi PowerApps wypełnione sformatowanymi danymi wykorzystywanymi w aplikacjach PowerApp i przepływach.

> [!Important]
> Przed usunięciem środowiska usługi PowerApps upewnij się, że nie jest ono używane do integrowania sformatowanych danych poza zakresem modułu Talent. Należy również zwrócić uwagę, że nie można usuwać domyślnych środowisk usługi PowerApps. 

Aby usunąć całe środowisko usługi PowerApps, w tym aplikację Talent oraz powiązane aplikacje i przepływy:

1. Przejdź do [centrum administracyjnego usługi PowerApps](https://admin.businessplatform.microsoft.com/).
2. Wybierz opcję **Środowiska**.
3. Zaznacz środowisko, które chcesz usunąć.
4. Wybierz opcję **Usuń** i potwierdź decyzję. 
5. Poczekaj na zakończenie usuwania.
6. Zaloguj się w usłudze [Lifecycle Services](https://lcs.dynamics.com/Logon/Index) (LCS) za pomocą konta użytego do zasubskrybowania aplikacji Talent. 
7. Wybierz projekt z aplikacją Talent , który zawiera środowisko. 
8. W projekcie LCS wybierz kafel **Zarządzanie aplikacją Talent**. 
9. Wybierz wystąpienie do usunięcia. 
10. Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję.  

Aby usunąć środowisko Talent z istniejącego środowiska usługi PowerApps, wykonaj następujące kroki. Należy zauważyć, że konieczność zaangażowania działu pomocy technicznej i skontaktowania się z zespołem DevOps aplikacji Talent są tymczasowe, do czasu włączenia tej funkcji bezpośrednio w usłudze LCS.

1. Skontaktuj się z działem pomocy technicznej i zainicjuj wniosek o usunięcie.
2. Dział pomocy technicznej zainicjuje wniosek o usunięcie razem z zespołem DevOps aplikacji Talent. 
3. Po otrzymaniu informacji, że środowisko zostało usunięte, kontynuuj procedurę.
4.  Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Talent. 
5. Wybierz projekt z aplikacją Talent , który zawiera środowisko. 
6. W projekcie LCS wybierz kafel **Zarządzanie aplikacją Talent**. 
7. Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Niepowodzenie**.
8. Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję. 


