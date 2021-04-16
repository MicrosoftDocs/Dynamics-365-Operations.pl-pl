---
title: Wycofaj konfiguracje w repozytorium globalnym RCS
description: W tym temacie opisano sposób wycofania konfiguracji w repozytorium globalnym RCS.
author: JaneA07
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 25ad0744e7c3320505c13c465d440b6a364da47c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840299"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Wycofaj konfiguracje w repozytorium globalnym RCS

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób wycofania konfiguracji w repozytorium globalnym RCS. Wcześniej można było usuwać tylko konfiguracje, które nie były już wymagane. Teraz jednak można oznaczyć zwolniną konfigurację jako **Wycofaną** w repozytorium globalnym RCS. Dzięki tej funkcji możesz również wykonać następujące czynności: 
 
 - Jeśli konfiguracja ma zostać przerwana, należy otrzymywać powiadomienia z góry.
 - Uwzględnij odpowiednie szczegóły dotyczące konfiguracji wymiany.
 - Ustaw obsługiwaną **Datę zakończenia** określonej konfiguracji, aby poinformować użytkownika o jej wycofaniu.

Po wycofaniu wersji konfiguracji można określić następujące informacje opcjonalne:

  - **Konfiguracja zastępcza**
  - **Zastępcza wersja konfiguracji**
  - **Dowolna uwaga tekstowa**: to pole pozwala na dostęp do łączy dokumentacji lub odwołań
  - **Obsługiwane do**: W tym polu jest proponowana data, do której będzie obsługiwana bieżąca konfiguracja/wersja. Należy ją zaktualizować ręcznie.
  
Aby przerwać konfigurację, wykonaj następujące kroki. 

1. Określ, czy chcesz przerwać pojedynczą, czy wszystkie wersje o tych samych ustawieniach w jednej operacji, ustawiając opcję **Wszystkie wersje** na **Tak**. 
2. Ustaw dla parametru **Wycofaj** wartość **Tak**.
3. Wybierz **OK**, aby przerwać konfiguracje. Podczas zapisywania zmian zostanie wypełnione pole **Data wycofania**.

![Wycofaj informacje o konfiguracji](media/Discontinue-details-2.png)
  
W dowolnym momencie można przywrócić konfigurację na **Udostępniono** lub skorygować informacje o wycofaniu. Po udostępnieniu konfiguracji należy określić **Obsługiwane do** do oraz wszystkie inne informacje dotyczące wycofania, aby wskazać plany przyszłego wycofania.

Aby udostępnić informacje dotyczące planowanego przerwania przed zakończeniem konfigurowania, użytkownik może wstępnie wypełnić wszystkie pola związane z wymianą, ale pozostawić parametr **Wycofaj** ustawiony na wartość **Nie**.

> [!NOTE]
> Przerwanie nie ogranicza operacji z konfiguracjami. Istnieje możliwość kontynuowania importowania, uruchamiania lub wyprowadzenia konfiguracji. Te pola zawierają informacje.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Funkcje finansowe obsługują wyświetlanie tych informacji w wersji 10.0.14

Począwszy od wersji 10.0.14, Dynamics 365 Finance obsługuje wyświetlanie informacji o wycofaniu. Na stronie **Repozytorium globalnym** można wyświetlać aktualne informacje związane z przerwaniem. Domyślnie konfiguracje wycofane są odfiltrowywowane.
  
Strona **Konfiguracje zaimportowane** (ERSolutionTable) zawiera konfiguracje, które zostały już wycofane podczas importowania. W przypadku konfiguracji, które zostały wycofane po imporcie, informacje o wycofaniu można zsynchronizować, uruchamiając zadanie **Importuj aktualizacje konfiguracji**.


