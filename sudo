import subprocess
import sys


def run_as_admin(command):

    command_line = f"PowerShell -Command Start-Process \"{command}\" -Verb RunAs"

    try:
        result = subprocess.run(command_line, shell=True, check=True)

        if result.returncode == 0:
            print(f"Команда \"{command}\" успешно выполнена с правами администратора.")
        else:
            print(f"Ошибка при выполнении команды \"{command}\". Код возврата: {result.returncode}")

    except subprocess.CalledProcessError as e:
        print(f"Произошла ошибка при выполнении команды \"{command}\".")
        print(f"Ошибка: {e}")


if __name__ == "__main__":
    if len(sys.argv) < 2:
        print("Использование: sudo [команда]")
        sys.exit(1)

    command = " ".join(sys.argv[1:])
    run_as_admin(command)
