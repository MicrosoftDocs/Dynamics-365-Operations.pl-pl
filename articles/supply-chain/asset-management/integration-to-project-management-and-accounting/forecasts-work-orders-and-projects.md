---
title: Prognozy, zlecenia pracy i projekty
description: W tym temacie objaśniono prognozy i integrację zleceń pracy z modułem Zarządzanie projektami i ich księgowanie w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e527a1ade9b050c0700ef42bbcac8da3f36160b9
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571790"
---
# <a name="forecasts-work-orders-and-projects"></a>Prognozy, zlecenia pracy i projekty

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku integracja z modułem **Zarządzanie projektami i ich księgowanie** odbywa się w celu zoptymalizowania kontroli kosztów, pozwalając użytkownikom na śledzenie kosztów dotyczących prognoz typów zadań konserwacji i zleceń pracy.

Aby śledzić prognozy typów zadań konserwacji, należy wykonać dwa ustawienia:

1. Wybierz projekt w **Zarządzanie składnikami majątku** > **Ustawienia** > **parametry zarządzania składnikami majątku**, następnie na karcie **Składnik majątku** > na karcie skróconej **Projekt** w **Projekt prognozy konserwacji** wybierz projekt.

2. Podczas tworzenia wiersza domyślnego typu zadania jest automatycznie tworzony numer działania dla wiersza na stronie **Domyślny typ zadania konserwacji** (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zadania** > **Ustawienia domyślne typu zadania konserwacji**).

Prognozy typu zadania obsługi służą do dwóch celów: 

- Koszty dotyczące prognoz typów zadań eksploatacji można śledzić w module **Zarządzanie projektami i ich księgowanie**. 
- Ponadto prognozy są automatycznie przenoszone do projektu zadania zlecenia pracy po wybraniu typu zadania konserwacji w zadaniu zlecenia.

Aby śledzić koszty zadań zlecenia pracy, należy najpierw skonfigurować projekty zleceń pracy. Aby uzyskać więcej informacji, zobacz [Ustawienia projektu zlecenia pracy](../setup-for-work-orders/work-order-project-setup.md).

## <a name="work-order-job-projects"></a>Projekty zadania zlecenia pracy

W przypadku tworzenia zadania zlecenia pracy w zleceniu pracy, projekt zlecenia jest określany na podstawie ustawień projektu nadrzędnego dla zlecenia pracy na stronie **Ustawienia projektu zlecenia pracy** (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Ustawienia projektu**).

Projekty zadań zlecenia są tworzone przy użyciu kombinacji następujących informacji o zleceniu pracy:

- Typ zlecenia pracy wybrany w zleceniu pracy 
- Lokalizacja czynności konserwacyjnych związana z składnikiem majątku w zadaniu zlecenia pracy
- Typ składnika majątku związany z składnikiem majątku w zadaniu zlecenia pracy  
- Oczekiwany czas rozpoczęcia i zakończenia zlecenia pracy  

Niektóre z tych informacji mogą nie zostać znalezione w zleceniu produkcyjnym. Dlatego wyszukiwanie projektu nadrzędnego zlecenia pracy jest wykonywane przy użyciu dostępnej kombinacji danych i wybierania identyfikatora projektu, który odpowiada danym zleceniom pracy.

Na przykład na poniższej ilustracji, ze względu na sposób skonfigurowania typu środków trwałych **silnika samochodowego**, każde zadanie zlecenia utworzone z typem środka trwałego **silnika samochodowego** będzie podprojektem identyfikatora projektu 000186.

![Rysunek 1](media/01-integration-to-pma.png)

Cel identyfikatora projektu w zadaniu zlecenia produkcyjnego oraz związany z nim numer działania to śledzenie kosztów związanych z zadaniem zlecenia, a następnie wybranie środka trwałego w module **Zarządzanie projektami i ich księgowanie** (Aby wyświetlić identyfikator projektu i numer działania, należy wybrać **Zarządzanie składnikami majątku** > **Wspólne** > **Zlecenia pracy** > **Wszystkie zlecenia pracy**, a następnie wybrać zlecenie pracy. W przypadku skróconej karcie **szczegółów wiersza** w polu **identyfikator projektu** wyświetlany jest identyfikator projektu, a w polu **numer działania** wyświetlany jest numer działania.) Aby uzyskać więcej informacji na temat kontroli kosztów w module Zarządzanie składnikami majątku przejrzyj [Kontrola kosztów i dat](../controlling-and-reporting/cost-and-date-control.md).

Na poniższym rysunku widać graficzny przegląd projektów zleceń i powiązanych z nimi działań projektu.

![Rysunek 2](media/02-integration-to-pma.png)

Podczas tworzenia nowego zadania zlecenia pracy w zleceniu pracy automatycznie tworzony jest projekt zlecenia produkcyjnego. Wymiary finansowe dla składnika majątku związanego z zadaniem zlecenia są automatycznie przenoszone do projektu zlecenia pracy.

Do zadań związanych z projektem, które są tworzone dla zadania zlecenia produkcyjnego, są dołączone informacje związane z danym zadaniem. Te informacje dotyczą typu zadania konserwacji, wariantu typu zadania obsługi oraz handlu. Dane są przydatne, jeśli na przykład zamówienie zakupu jest tworzone na podstawie zlecenia pracy (patrz [Zaopatrzenie](../work-orders/procurement.md)) lub jeśli do rejestracji czasu jest używany moduł **Zarządzanie projektami i ich księgowanie**.

Jeśli składnik majatku został zainstalowany w lokalizacji czynności konserwacyjnych, a ten składnik jest później instalowany w innej lokalizacji czynności konserwacyjnych, wymiary finansowe związane z nową lokalizacją czynności konserwacyjnych są automatycznie aktualizowane na tym składniku. Następnie podczas tworzenia zadania zlecenia pracy dla skłądnika majątku projekt zlecenia zadania automatycznie otrzymuje wymiary finansowe, które są obecnie powiązane z danym składnikiem. Oznacza to, że w przypadku korzystania z lokalizacji czynności konserwacyjnych koszty mogą być zawsze śledzone w lokalizacjach czynności konserwacyjnych, w których dany składnik został zainstalowany w danym momencie. Automatyczna aktualizacja wymiarów finansowych pomaga zapewnić pełne śledzenie kosztów związanych z kontrolowaniem i raportowaniem projektów.

## <a name="work-order-projects-work-order-lifecycle-states-project-stages-and-project-types"></a>Projekty zleceń pracy, Stany cyklu życia zleceń pracy, etapy projektu i typy projektów

Aby zapewnić poprawne wykorzystanie stanów cyklu życia zlecenia pracy i powiązanych etapów projektu w zleceniach pracy, należy wziąć pod uwagę zależności w module **Zarządzanie projektami i ich księgowanie**:

- W module **Zarządzanie projektami i księgowanie** etapy projektu są ustawiane na typy projektów na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie**.  
- Na stronie **Parametry modułu Zarządzanie projektami i ich księgowanie** należy pamiętać o zaznaczeniu odpowiednich pól wyboru dla wszystkich etapów projektów, które mają być używane. Na poniższym rysunku jest pięć etapów (**Utworzony**, **Oszacowanie**, **Zaplanowane**, **W toku** i **Zakończony**) zostały wybrane dla typów pojektów **Czas i materiał** i **Wewnętrzne**. Te pięć etapów są istotne zarówno dla zadań konserwacji wewnętrznej, jak i zadań konserwacji.
- W module **Zarządzanie składnikami majątku** typy projektów są definiowane przez grupy projektów określone na stronie **Konfiguracja projektu zlecenia pracy** > karta **Grupa projektów** (**Zarządzanie składnikami majątku** > **Ustawienia** > **Zlecenia pracy** > **Konfiguracja projektu**).  
- Ustawienia grup projektów na stronie **Ustawienia projektu zlecenia pracy** są używane podczas tworzenia zleceń pracy. Podczas tworzenia nowego zlecenia pracy, projekt zlecenia pracy jest automatycznie tworzony dla danego zlecenia pracy.  
- Każdy stan cyklu życia zlecenia pracy musi mieć powiązany etap projektu.  
- Etap projektu związany ze stanem cyklu życia zlecenia pracy musi być zdefiniowany jako aktywny etap dla grupy projektów zdefiniowanej w projekcie zlecenia pracy. W zleceniu pracy automatycznie tworzony jest projekt zlecenia pracy.
- W przypadku tworzenia nowego zlecenia pracy automatyczne przydzielanie projektu zlecenia pracy jest oparte na konfiguracji na stronie **Ustawienia projektu zlecenia pracy**.  

Powiązania między grupami projektów zlecenia pracy, powiązane typy projektów, etapy projektu i Stany cyklu życia zlecenia pracy są przedstawione poniżej na ilustracji.

![Rysunek 3](media/03-integration-to-pma.png)

![Rysunek 4](media/04-integration-to-pma.png)

![Rysunek 5](media/05-integration-to-pma.png)

Aby uzyskać więcej informacji na temat konfigurowania projektów zleceń pracy, zobacz temat [Konfigurowanie typów zleceń pracy](../setup-for-work-orders/work-order-project-setup.md). Aby uzyskać więcej informacji na temat tworzenia stanów cyklu życia zlecenia pracy, należy zapoznać się z [Stany cyklu życia zlecenia pracy](../setup-for-work-orders/work-order-lifecycle-states.md).

Na poniższej ilustracji przedstawiono graficzny przegląd różnych projektów utworzonych w module **Zarządzanie środkami trwałymi** w celu włączenia integracji z modułem **Zarządzanie projektami i ich księgowanie**. Pokazuje także procesy robocze, z którymi są powiązane projekty.

![Rysunek 6](media/06-integration-to-pma.png)

