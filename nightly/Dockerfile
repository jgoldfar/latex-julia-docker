FROM jgoldfar/latex-julia-docker:reqs-latest

# Make sure we don't get notifications we can't answer during building.
env DEBIAN_FRONTEND noninteractive

LABEL maintainer "Jonathan Goldfarb <jgoldfar@my.fit.edu>"

# Install Julia 0.7
## Set environment variables to change "old" version of Julia
ENV JuliaOldVerShort 0.7
ENV JuliaOldVer 0.7.0
ENV JuliaOldVerString julia-${JuliaOldVer}
ENV JuliaOldPath /opt/${JuliaOldVerString}
RUN mkdir -p ${JuliaOldPath} && \
    curl -s -L https://julialang-s3.julialang.org/bin/linux/x64/${JuliaOldVerShort}/${JuliaOldVerString}-linux-x86_64.tar.gz | \
    tar -C ${JuliaOldPath} -x -z --strip-components=1 -f - && \
    ln -fs ${JuliaOldPath} /opt/julia-${JuliaOldVerShort} && \
    ln -s /opt/julia-${JuliaOldVerShort}/bin/julia /usr/local/bin/julia-${JuliaOldVerShort}

# Install Julia 1.0
## Set environment variables to change "current" version of Julia
ENV JuliaVerShort 1.0
ENV JuliaVer 1.0.0
ENV JuliaVerString julia-${JuliaVer}
ENV JuliaPath /opt/${JuliaVerString}
RUN mkdir -p ${JuliaPath} && \
    curl -s -L https://julialang-s3.julialang.org/bin/linux/x64/${JuliaVerShort}/${JuliaVerString}-linux-x86_64.tar.gz | \
    tar -C ${JuliaPath} -x -z --strip-components=1 -f - && \
    ln -fs ${JuliaPath} /opt/julia-${JuliaVerShort} && \
    ln -s /opt/julia-${JuliaVerShort}/bin/julia /usr/local/bin/julia-${JuliaVerShort} && \
    ln -s /opt/julia-${JuliaVerShort}/bin/julia /usr/local/bin/julia
