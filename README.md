mkdir MyCleanArch
cd MyCleanArch
dotnet new sln -n MyCleanArch

dotnet new classlib -n Domain -o src/Domain
dotnet new classlib -n Application -o src/Application
dotnet new classlib -n Infrastructure -o src/Infrastructure
dotnet new webapi -n Web -o src/Web

dotnet sln add src/Domain src/Application src/Infrastructure src/Web

dotnet add src/Application reference src/Domain
dotnet add src/Infrastructure reference src/Application
dotnet add src/Web reference src/Application
dotnet add src/Web reference src/Infrastructure
