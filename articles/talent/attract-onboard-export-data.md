---
title: Eksportowanie danych z Attract i Onboard
description: Eksportowanie danych z Dynamics 365 Talent - Attract i Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462178"
---
# <a name="export-data-from-attract-and-onboard"></a>Eksportowanie danych z Attract i Onboard

[!include [banner](includes/banner.md)]

Zgodnie z informacjami w [Wycodywanie aplikacji Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), wycofujemy aplikacje Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard  1 lutego 2022. Aby ułatwić migrację do innego produktu, w obu tych aplikacjach są dostępne funkcje eksportu danych.

## <a name="export-data-from-attract"></a>Eksportowanie danych z Attract

Można eksportować dane bez ograniczania dostępu do środowiska. Może to być przydatne w celach testowych lub do zrozumienia struktury danych. Gdy wszystko będzie gotowe do migracji, należy ograniczyć dostęp do środowiska Attract, korzystając z instrukcji opisanej po tej procedurze. Należy pamiętać o ponownym wyeksportowaniu danych. 

1. Przejdź do [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. W obszarze **Eksportowanie danych** wybierz opcję **Żądaj eksportu danych**.

   ![[Zażądaj eksportu danych z Attract](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. Po wyświetleniu okna komunikatu, **Twoje żądanie jest przetwarzane** wybierz **OK**. Eksport danych może potrwać do 20 minut, w zależności od rozmiaru eksportu.

4. Po zakończeniu eksportu wybierz znajdujący się obok przycisk **Pobierz**. 

   >[!NOTE]
   >Wszystkie operacje eksportu danych są dostępne przez siedem dni, w którym łącze **Pobierz** wygasa.</br>
   
Pobieranie zawiera plik .zip z danymi Attract, w tym następujące foldery:

| Nazwa folderu | Opis |
| --- | --- |
| Ustawienia administratora | Konfiguracja centrum administracyjnego Attract. |
| Kandydaci | Wszyscy kandydaci, którzy zostali dodani do zadań lub pul talentów. |
| Szablony wiadomości e-mail | Wszystkie szablony wiadomości e-mail skonfigurowane dla środowiska. |
| Szablony pakietów ofert pracy | Wszystkie utworzone szablony pakietu ofert pracy oraz skojarzone z nimi konfiguracje. |
| Zestawy reguł oferty pracy |  Wszystkie pliki zestawów reguł przekazane dla zarządzania ofertami. |
| Szablony ofert pracy | Wszystkie szablony dokumentów ofert pracy utworzone dla środowiska. |
| Wakaty | Wszystkie utworzone zadania. Usunięte zadania nie są eksportowane. Podfoldery zawierają aplikacje kandydatów, z podfolderami służącymi do umieszczania załączników w aplikacjach kandydatów i oferują pakiety ofert, gdzie ma to zastosowanie. |
| Szablony wakatów | Szablony procesu zadania skonfigurowane dla środowiska. |
| Pule umiejętności i kandydatów | Wszystkie utworzone pule talentów, ich listy współautorów oraz listy kandydatów dla pul talentów. |
| Pracownicy | Lista wszystkich pracowników, którzy są obecni w środowisku, oraz ich role. |
| (folder główny) | Plik schematu JSON opisujący pola struktury danych. |

### <a name="restrict-access-to-attract"></a>Ogranicz dostęp do Attract

Po przygotowaniu się do migracji można ograniczyć dostęp innych niż administratorzy do środowiska Attract i eksportować dane.

>[!IMPORTANT]
>Ograniczenie dostępu do środowiska Attract jest trwałe i nie można go cofnąć. Jeśli chcesz, aby użytkownicy inni niż administratorzy mogli nadal uzyskiwać dostęp do środowiska, pomiń ten krok.

1. Przejdź do [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).

2. W celu ograniczenia dostępu do środowiska przyciągania w systemie innym niż administratorzy, w obszarze **Ogranicz dostęp do tej aplikacji** wybierz pozycję **Ogranicz dostęp teraz**. Ograniczenie dostępu powoduje także wykonuje wyksięgowanie wszystkich aktywnych zadań, które zostały zaksięgowane.

   ![[Ogranicz dostęp dla osób innych niż administrator do Attract](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. Po wyświetleniu ostrzeżenia jest **To stała zmiana**, zaznacz opcję **Ogranicz dostęp**, aby trwale ograniczyć liczbę użytkowników niebędących administratorami w tym środowisku. Jeśli nie masz gotowości do wykonania tego kroku, wybierz przycisk **Anuluj**.

   ![[Ostrzeżenie, że ograniczenie dostępu jest stałą zmianą](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   >Administratorzy mogą nadal uzyskiwać dostęp do stron eksport danych i raportów o osobach po ograniczeniu dostępu do środowiska Attract.

## <a name="export-data-from-onboard"></a>Eksportowanie danych z rozwiązania Onboard

Gdy wszystko będzie gotowe, można pobrać szablony, przewodniki i dane kandydatów z systemu na Onboard.

1. Przejdź do [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).

2. W obszarze **Eksportowanie danych** wybierz opcję **Żądaj eksportu danych**. 

   ![[Zażądaj eksportu danych z Onboard](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. Po wyświetleniu okna komunikatu, **Twoje żądanie jest przetwarzane** wybierz **OK**. Eksport danych może potrwać do 20 minut, w zależności od rozmiaru eksportu.

4. Po zakończeniu eksportu wybierz znajdujący się obok przycisk **Pobierz**. 

   ![[Pobieranie danych eksportowanych z rozwiązania Onboard](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   >Eksport danych jest dostępny przez siedem dni. Po siedmiu dniach łącze **Pobierz** wygaśnie i trzeba będzie zażądać nowego eksportu, jeśli trzeba będzie ponownie pobrać dane. Po uruchomieniu nowego eksportu danych wszelkie istniejące pliki do pobrania wygasną po pomyślnym zakończeniu nowego eksportu.

Pobierany plik jest plikiem .zip zawierający:

- Folder **Szablony**, który zawiera szablony Onboard w formacie dokumentu programu Word.

- Folder **Guides**, który zawiera przewodniki Onboard w formacie dokumentu programu Word.

## <a name="see-also"></a>Informacje dodatkowe

[Wycofywanie aplikacji Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)