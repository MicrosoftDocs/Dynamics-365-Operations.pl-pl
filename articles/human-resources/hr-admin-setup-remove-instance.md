---
title: Usuwanie wystąpienie
description: Ten artykuł przeprowadzi użytkownika przez proces usuwania środowiska testowego lub produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4256938be70f301d3d7b7663f10addb19725b048
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859641"
---
# <a name="remove-an-instance"></a>Usuwanie wystąpienie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule wyjaśniono przebieg procesu usuwania wersji testowej lub środowiska produkcyjnego dla oprogramowania Microsoft Dynamics 365 Human Resources.

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
4. Zaloguj się w usłudze LCS za pomocą konta używanego do subskrypcji rozwiązania Human Resources. 
5. Wybierz projekt z aplikacją Human Resources, który zawiera środowisko. 
6. W projekcie LCS wybierz kafelek **Zarządzanie aplikacją Human Resources**. 
7. Zaznacz wystąpienie, które chcesz usunąć. Powinno być ono oznaczone stanem wdrożenia **Usunięte**.
8. Wybierz opcję **Usuń wystąpienie** i potwierdź decyzję. 

## <a name="recover-a-soft-deleted-environment"></a>Odzyskiwanie wstępnie usuniętego środowiska

W przypadku usunięcia środowiska Power Apps, z którym jest połączone środowisko Human Resources, stan środowiska Human Resources w usługach w ramach Lifecycle Services zostanie **Delikatnie usunięty**. W takim przypadku użytkownicy nie mogą łączyć się z Human Resources.

Aby przywrócić środowisko:

1. Wykonaj instrukcje w [Odzyskaj środowisko Power Apps](/power-platform/admin/recover-environment).

2. Skontaktuj się z pomocą techniczną w celu przywrócenia środowiska Human Resources. Aby uzyskać więcej informacji, zobacz [Uzyskiwanie pomocy technicznej](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).

> [!Warning]
> Środowiska Power Apps są zapisywane tylko przez siedem dni po usunięciu. Musisz odzyskać środowisko w okresie siedmiu dni.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
