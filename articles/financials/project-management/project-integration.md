---
title: Integracja z klientem Microsoft Project
description: "Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie. Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a3445417d5ae88e2ff3676962a82921a7ab475d
ms.contentlocale: pl-pl
ms.lasthandoff: 03/26/2018

---

# <a name="microsoft-project-client-integration"></a>Integracja z klientem Microsoft Project

[!include[banner](../includes/banner.md)]

Planowanie harmonogramu projektu i zarządzanie nim może być skomplikowane, dlatego menedżerowie projektów powinni używać narzędzi, które pomogą wykonywać to zadanie. Integracja z klientem programu Microsoft Project umożliwia otwieranie struktury podziału pracy projektu oraz zarządzanie nią. Menedżer projektu może publikować wszelkie zmiany z powrotem w strukturze podziału pracy projektu w programie Finance and Operations.

> [!NOTE]
> Jeśli używasz programu Microsoft Dynamics 365 for Finance and Operations z lipcową aktualizacją, należy zainstalować poprawki KB 4054797 i 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Konfigurowanie dodatku klienta programu Microsoft Project
Aby umożliwić integrację z klientem programu Microsoft Project, w aplikacji klienckiej Microsoft Project u użytkownika musi być zainstalowany dodatek usługi Microsoft Dynamics 365. W tym celu należy otworzyć **obszar roboczy Zarządzanie projektami**.

•   W obszarze roboczym w sekcji **Łącza** > **Ustawienia** kliknij przycisk **Konfiguruj dodatek klienta programu Project** .

•   Kliknij przycisk **Otwórz**, następnie po pojawieniu się monitu kliknij przycisk **Uruchom**.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Otwieranie i edytowanie istniejącej wersji roboczej struktury podziału pracy w kliencie programu Microsoft Project
Jeżeli projekt w programie Finance and Operations ma już utworzoną strukturę podziału pracy, można ją otworzyć w aplikacji klienckiej Microsoft Project, o ile tylko struktura jest wersją roboczą. Aby otworzyć strukturę ze strony **Projekt**, na karcie **Plan** kliknij łącze **Otwórz w programie Microsoft Project**. Tę stronę można również otworzyć z poziomu aplikacji klienckiej Microsoft Project, klikając przycisk **Otwórz** na karcie **Microsoft Dynamics 365**. Wybierz opcję **Firma**, a następnie na liście pozycję **Projekt**.

> [!NOTE]
> Jeśli używasz przeglądarki Internet Explorer, trzeba będzie kliknąć przycisk **Zapisz** i ręcznie otworzyć plik z lokalizacji, do której zostanie pobrany. Można też kliknąć opcję **Zapisz i otwórz** i otworzyć plik w kliencie programu Microsoft Project. Podczas zapisywania nie zmieniaj nazwy pliku.

Przed wprowadzeniem jakichkolwiek zmian w pliku przy użyciu klienta programu Microsoft Project należy go wyewidencjonować. Kliknij przycisk **Wyewidencjonuj** na karcie **Microsoft Dynamics 365**. Uniemożliwi to innym użytkownikom edytowanie struktury podziału pracy w tym samym czasie z poziomu programu Finance and Operations. Aby opublikować strukturę podziału pracy po wprowadzeniu wszelkich zmian, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.

Jeśli zespół projektu został już dodany do projektu w programie Finance and Operations, na liście zasobów zostaną wstawieni członkowie zespołu. Jeśli zespół projektu nie został jeszcze dodany do projektu, można wybrać zasoby i zbudować zespół w kliencie programu Microsoft Project, klikając przycisk **Zasoby** znajdujący się na karcie **Microsoft Dynamics 365**. 

Następujące dane zostaną zsynchronizowane z powrotem z programem Finance and Operations w ramach procesu ewidencjonowania:

•   Nazwa zadania

•   Data rozpoczęcia

•   Data zakończenia

•   Zdarzenia poprzedzające

•   Nazwy zasobów

•   Kategoria

•   Kategoria zasobów

•   Godziny pracy

•   Notatki

•   Priorytet

> [!NOTE]
> Jeśli do pliku klienta programu Microsoft Project zostaną dodane jakiekolwiek inne kolumny, nie zostaną one zapisane w pliku i nie pojawią się po ponownym otwarciu pliku.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Tworzenie struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project
Aby utworzyć nową strukturę podziału pracy przy użyciu klienta programu Microsoft Project, wykonaj następujące czynności:


1.  Otwórz klienta programu Microsoft Project.

2.  Na karcie **Microsoft Dynamics 365** kliknij przycisk **Otwórz**.

3.  Wybierz dla projektu wartość w polu **Firma**.

4.  Wybierz opcję **Projekt**.

5.  Na karcie **Microsoft Dynamics 365** kliknij przycisk **Wyewidencjonuj**.

6.  Gotowy masz wszystko przygotowane do publikowania w programie Finance and Operations, na karcie **Microsoft Dynamics 365** kliknij przycisk **Zaewidencjonuj**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Zastępowanie istniejącej struktury podziału pracy dla istniejącego projektu przy użyciu klienta programu Microsoft Project
Aby utworzyć nową strukturę podziału pracy za pomocą klienta programu Microsoft Project i zastąpić nią istniejącą strukturę podziału pracy dla istniejącego projektu, wykonaj następujące kroki:

1.  Otwórz klienta programu Microsoft Project.

2.  Utwórz harmonogram w kliencie programu Microsoft Project.

3.  Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zastąp istniejący projekt**.

4.  Wybierz dla projektu wartość w polu **Firma**.

5.  Wybierz opcję **Projekt**.

6.  Kliknij przycisk **OK**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Tworzenie nowego projektu z klienta programu Microsoft Project


1.  Otwórz klienta programu Microsoft Project.

2.  Utwórz harmonogram w kliencie programu Microsoft Project.

3.  Na karcie **Microsoft Dynamics 365** kliknij kolejno opcje **Zapisz zmiany** > **Zapisz do nowego projektu**.

4.  Wybierz dla projektu wartość w polu **Firma**.

5.  W razie potrzeby wypełnij pole **Identyfikatora projektu**.

6.  Wypełnij pole **Nazwa projektu**.

7.  Wybierz wartości w polach **Typ projektu**, **Grupa projektów** i **Identyfikator umowy dotyczącej projektu**. Alternatywnie można utworzyć nową umowę na projekt, klikając przycisk **Nowy**.

8.  Wybierz wartość w polu **Kalendarz** na potrzeby pozyskiwania zasobów.

11. Kliknij przycisk **OK**.

