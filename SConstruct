import excons
import excons.cmake
from excons.tools import nuke

env = excons.MakeBaseEnv()
nuke.Require(env)
nuke_path = excons.GetArgument("with-nuke")
cmake_opts = {"Nuke_ROOT": nuke_path}

proj = [
    {
        "name": "DeepC",
        "type": "cmake",
        "cmake-opts": cmake_opts,
        "cmake-cfgs": excons.CollectFiles(".", patterns=["CMakeLists.txt"], recursive=True),
        "cmake-srcs": excons.CollectFiles(".", patterns=["*.c", "*.os"], recursive=True),
    }
]

env.Append(CPPPATH=["FastNoise"])

excons.AddHelpOptions(
     DeepC=
        """
        """
    )

excons.DeclareTargets(env, proj)