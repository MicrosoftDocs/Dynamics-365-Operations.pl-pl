---
title: Utwórz konto magazynu Azure i Magazyn kluczy
description: W tym temacie opisano sposób tworzenia konta magazynu Azure i magazynu kluczy.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 23fec7a00d800719e1a7d2c90f9d0977d56be038
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463868"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a>Utwórz konto magazynu Azure i Magazyn kluczy

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Wymagania wstępne

Zanim będzie można wykonać czynności opisane w tym temacie, należy upewnić się, że wykonano następujące zadania:

- Tworzenie zasobu magazynu kluczy w Azure. Aby uzyskać więcej informacji o tej funkcji, zobacz: [Informacje o usłudze Azure Key Vault](/azure/key-vault/general/overview).
- Utwórz konto magazynu Azure (magazyn obiektów BLOB). Aby uzyskać więcej informacji, przejrzyj temat [Obsługa konta magazynu Azure](/azure/storage/blobs/).

## <a name="overview"></a>Omówienie

W tym temacie przedstawiono dwa główne kroki:

- Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu.
- Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu.

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a>Skonfiguruj konto magazynu Azure, aby uzyskać identyfikator URI konta magazynu

1. Umożliwia otwarcie konta magazynu, które ma być używane z funkcją Faktury elektroniczne.
2. Przejdź do **Magazyn danych** > **Kontenery** i utwórz nowy kontener.
3. Wprowadź nazwę kontenera i ustaw dla pola **Poziom dostępu publicznego** wartość **Prywatne (brak dostępu anonimowego)**.
4. Otwórz kontener i przejdź do **Ustawienia** > **Zasady dostępu**.
5. Wybierz opcję **Dodaj zasady**, aby dodać zapisane zasady dostępu.
6. Odpowiednio określ **Identyfikator** i pola **Uprawnień**. W polu **uprawnienia** zaznacz opcję wszystkie uprawnienia.

    ![Przyznawanie uprawnień do magazynu obiektów Blob.](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. Wprowadź daty rozpoczęcia i ważności. Data ważności powinna być w przyszłości.
8. Wybierz przycisk **OK**, aby zapisać zasady, a następnie zapisz zmiany w kontenerze.
9. Przejdź do **Ustawienia** > **Udostępnione tokeny dostępu** i ustaw wartości pól. 
10. Wprowadź daty rozpoczęcia i zakończenia. Data zakończenia powinna być w przyszłości.
11. W polu **Uprawnienia** wybierz następujące uprawnienia: **Odczyt**, **Dodawanie**, **Tworzenie**, **Zapis**, **Usuwanie** i **Lista**. 
12. Wybierz pozycję **Generuj token SAS i adres URL**.
13. Skopiuj i przechowaj wartość w polu **adresu URL SAS obiektu blob**. Ta wartość będzie używana w następnej procedurze i jest określana jako *Identyfikator URI podpisu dostępu współdzielonego*.

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a>Skonfiguruj Magazyn kluczy do przechowywania identyfikatora URI konta magazynu

1. Otwórz magazyn kluczy, którego zamierzasz używać z Faktury elektroniczne.
2. Przejdź do **Ustawienia** \> **Wpis tajny**, a następnie wybierz opcję **Generuj/Importuj**, aby utworzyć nowy wpis tajny.
3. Na stronie **Tworzenie wpisu tajnego** w polu **Opcje przekazywania** wybierz opcję **Ręcznie**.
4. Pozwala wprowadzić nazwę wpisu tajnego. Ta nazwa będzie używana podczas instalacji usługi w usłudze Regulatory Configuration Service (RCS) i będzie nazywana *nazwą klucza tajnego magazynu kluczy*.
5. W polu **Wartość** wprowadź identyfikator URI sygnatury dostępu współdzielonego skopiowany w poprzedniej procedurze, a następnie wybierz polecenie **Utwórz**.
6. Skonfiguruj zasady dostępu, aby nadać funkcji Faktury elektroniczne odpowiedni poziom bezpiecznego dostępu do utworzonego klucza tajnego. Przejdź do **Ustawienia \> Zasad dostępu** i wybierz pozycję **Dodaj zasady dostępu**.
7. Umożliwia ustawienie tajnych uprawnień dla operacji **Rozpocznij** i **Lista**.

    ![Udzielanie dostępu do usługi.](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. Umożliwia ustawienie certyfikatu uprawnień dla operacji **Rozpocznij** i **Lista**.

    ![Nadanie certyfikatu uprawnień.](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. W polu **Wybierz główny** wybierz opcję **Brak zaznaczonego**.
10. W oknie dialogowym **Główne** wybierz podmiot zabezpieczeń, dodając **Usługi e-fakturowania**.
11. Zaznacz element **Dodaj** i kliknij przycisk **Zapisz**.
12. Na stronie **Przegląd** skopiuj wartość **Nazwa DNS** dla magazynu kluczy. Ta wartość będzie używana podczas instalacji usługi w RCS i będzie określana jako *Identyfikator URI magazynu kluczy*.

> [!NOTE]
> Aby uzyskać dodatkowe zabezpieczenia konta magazynu, skonfiguruj funkcję Azure Defender for Storage.
> 
> Aby uzyskać więcej informacji, zobacz [Wprowadzenie do funkcji Azure Defender for Storage](/azure/security-center/defender-for-storage-introduction).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
